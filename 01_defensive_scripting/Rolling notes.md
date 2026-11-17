# Lab 01: Defensive Scripting & Guard Clauses

## Objective
Validate user input and verify file existence before executing main script logic.

## Core commands
* **`mkdir`**: Makes a directory/folder
* **`touch`**: Creates/updates a file
* **`echo`**: Prints text from a file
* **`ls`**: Displays full folder contents -la for more information
* **`rm`**: Deletes folder/file
* **`chmod`**: Change Mode — Modifies file read, write, and execute permissions. +x can be used to add execute permissions
* **`>`**: Overwrite, sends command output into a file
* **`>>`**: Adds command output to the bottom of a file without deleting existing lines
* **`<< 'EOF'`**: Feeds multiple lines of text into a command
* **`apropos`**: Helps find commands based on description such as apropos remove files
* **`Whatis`**: Gives a brief description of the command ie whatis ls
* **`man`**: `**: Man followed by a command such as man ls takes me to the documentation for that command

## Core Mechanics & Flags Used
* **`$1`**: Captures the first positional argument passed at runtime.
* **`-z "$VAR"`**: Returns true if the string is empty (zero length).
* **`! -f "$VAR"`**: Returns true if the target path does not exist or is not a regular file.
* **`exit 1`**: Terminates execution immediately with a non-zero error code.

## Bug Log & Debugging Takeaways
* **Issue:** Used `echo << 'EOF'` instead of `cat << 'EOF'`, resulting in an empty script file.
* **Fix:** Replaced with `cat` so standard input streams properly into the target file.
* **Issue:** Guard clause passed silently on a non-existent file because `TARGET_FILE=$1` wasn't assigned at the top of the test file.
* **Fix:** Always assign positional arguments before evaluating conditional checks.