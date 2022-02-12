warn("More than 500 changed lines of code") if git.lines_of_code > 500
warn("More than 25 added/modified files") if (git.added_files.length() + git.modified_files.length()) > 25

kotlin_detekt.skip_gradle_task = true
kotlin_detekt.report_file = "build/reports/detekt/detekt.xml"
kotlin_detekt.detekt(inline_mode: true)

lint_report_dir = "build/reports/lint/merged-lint-results.xml"
Dir[lint_report_dir].each do |file_name|
    android_lint.skip_gradle_task = true
    android_lint.report_file = file_name
    android_lint.lint(inline_mode: true)
end