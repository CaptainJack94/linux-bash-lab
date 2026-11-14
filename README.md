# Create your main README
@"
# Linux & Bash Engineering Lab

## Progress Log

| Lab | Topic | Key Concepts | Status |
| :--- | :--- | :--- | :--- |
| **01** | Defensive Scripting | `if/fi`, `$1`, `-z`, `! -f`, `exit 1`, Here-Docs (`EOF`) | Complete |
| **02** | Loops & Service Checks | `-d`, `||`, `while read -r`, `systemctl` exit codes | In Progress |
| **03** | Text Parsing & Logs | `grep`, `awk`, `sed`, stdout/stderr redirection | Planned |

First-principles Bash scripting, defensive system administration, and automation labs.

## Lab Index
* **01_defensive_scripting**: Input validation, guard clauses (`-z`, `! -f`), and exit codes.
* **02_loops_and_services**: Directory checks (`-d`, `||`) and line-by-line iteration (`while read -r`).
"@ | Out-File -Encoding utf8 README.md

# Create .gitignore
@"
*.log
*.tmp
.DS_Store
Thumbs.db
"@ | Out-File -Encoding utf8 .gitignore