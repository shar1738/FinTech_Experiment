VIDEO LINK (https://www.youtube.com/watch?v=I4EWvMFj37g) - Good little introduction video

BASH DOCUMENTATION (https://www.gnu.org/software/bash/manual/bash.html) - All info

# Bash Commands Cheat Sheet — Basic & Advanced

---

## 1) File & Directory Operations

| Command                        | Description                                        |
|--------------------------------|--------------------------------------------------|
| `ls`                            | List files and directories                        |
| `ls -l`                         | List with details (permissions, size, owner)     |
| `pwd`                           | Print current working directory                   |
| `cd /path/to/dir`               | Change directory                                  |
| `mkdir <dir>`                   | Create a new directory                            |
| `rmdir <dir>`                   | Remove empty directory                             |
| `rm <file>`                     | Delete a file                                     |
| `rm -r <dir>`                   | Delete a directory recursively                    |
| `cp <source> <dest>`            | Copy files or directories                         |
| `mv <source> <dest>`            | Move or rename files/directories                  |

---

## 2) Viewing & Manipulating Files

| Command                        | Description                                        |
|--------------------------------|--------------------------------------------------|
| `cat <file>`                    | Display file contents                              |
| `less <file>`                   | View file page by page                              |
| `head <file>`                   | View first 10 lines of file                         |
| `tail <file>`                   | View last 10 lines of file                          |
| `tail -f <file>`                | Continuously watch file updates                     |
| `grep "pattern" <file>`         | Search for text in file(s)                          |
| `wc <file>`                      | Count lines, words, and characters                 |

---

## 3) Variables & Arguments

| Command/Usage                   | Description                                        |
|--------------------------------|--------------------------------------------------|
| `VAR="value"`                    | Create a variable                                  |
| `echo $VAR`                      | Display variable value                             |
| `$1, $2, ...`                    | Access positional arguments passed to script     |
| `read VAR`                        | Read input from user into variable                |

---

## 4) Scripting Essentials

| Command/Usage                   | Description                                        |
|--------------------------------|--------------------------------------------------|
| `#!/bin/bash`                    | Shebang line to specify interpreter               |
| `chmod +x script.sh`             | Make script executable                             |
| `./script.sh`                    | Run script                                        |
| `echo "text"`                    | Print text to terminal                             |
| `if [ condition ]; then ... fi`  | Conditional execution                             |
| `while [ condition ]; do ... done` | Loop while condition is true                       |
| `for var in list; do ... done`   | Loop over items in a list                          |

---

## 5) Process Management

| Command                        | Description                                        |
|--------------------------------|--------------------------------------------------|
| `command &`                     | Run command in background                         |
| `jobs`                          | List background jobs                               |
| `fg %1`                          | Bring background job to foreground                |
| `ps`                            | Show running processes                             |
| `kill <pid>`                    | Terminate a process by PID                         |

---

## 6) Advanced / Useful Commands

| Command                        | Description                                        |
|--------------------------------|--------------------------------------------------|
| `history`                       | Show command history                               |
| `!!`                             | Repeat last command                                |
| `!n`                             | Repeat command number n from history              |
| `alias ll='ls -l'`              | Create shortcut command                            |
| `env`                            | Show environment variables                         |
| `export VAR=value`               | Set environment variable                            |
| `sleep <seconds>`                | Pause execution for given seconds                  |
| `date`                           | Show current date and time                         |
| `uptime`                         | Show system uptime                                  |
| `clear`                          | Clear terminal screen                               |

---

## 7) Input & Output Redirection

| Command                        | Description                                        |
|--------------------------------|--------------------------------------------------|
| `>`                             | Redirect output to file (overwrite)               |
| `>>`                            | Redirect output to file (append)                  |
| `<`                             | Redirect input from file                           |
| `|`                             | Pipe output to another command                     |
| `2>`                            | Redirect stderr to file                             |
| `&>`                            | Redirect stdout and stderr together               |

---

## 8) Quick Examples

```bash
# List all files including hidden
ls -a

# Search for "error" in log file
grep "error" /var/log/syslog

# Run script with arguments
./myscript.sh arg1 arg2

# Loop over files
for f in *.txt; do echo $f; done

# Conditional execution
if [ -f "file.txt" ]; then echo "File exists"; fi

# Background process
python long_task.py &
