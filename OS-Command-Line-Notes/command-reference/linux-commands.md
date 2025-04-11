# Linux Command Reference

## The Shell Environment

Linux typically uses the Bash shell (Bourne-Again SHell) as its default command interpreter, though there are many alternatives like Zsh, Fish, and others.

## Common Linux Commands

| Command | Description | Example |
|---------|-------------|---------|
| `ls` | List directory contents | `ls -la` |
| `cd` | Change directory | `cd ~/Documents` |
| `pwd` | Print working directory | `pwd` |
| `mkdir` | Create directory | `mkdir new_folder` |
| `rm` | Remove files/directories | `rm file.txt` |
| `cp` | Copy files/directories | `cp file.txt ~/backup/` |
| `mv` | Move/rename files | `mv old.txt new.txt` |
| `cat` | Concatenate and display files | `cat file.txt` |
| `less` | View file contents with pagination | `less large_file.log` |
| `head` | Show beginning of file | `head -n 5 file.txt` |
| `tail` | Show end of file | `tail -f log.txt` |
| `grep` | Search text patterns | `grep "error" log.txt` |
| `find` | Search for files | `find . -name "*.jpg"` |
| `man` | Display manual pages | `man ls` |
| `chmod` | Change file permissions | `chmod 755 script.sh` |
| `chown` | Change file owner | `chown user:group file.txt` |

## Command Flags/Options

Most Linux commands accept options (flags) that modify their behavior:

```bash
# Long format listing with human-readable sizes
ls -lh

# Recursive listing of all files including hidden ones
ls -laR
```

Common flag patterns:
- Single letter flags can be combined: `-la` is the same as `-l -a`
- Long-format flags use double dash: `--all` instead of `-a`

## Getting Help

```bash
# View manual page for a command
man ls

# Brief command help
ls --help

# Search through all manual pages
man -k "search term"
```

## File Permissions

Linux file permissions are represented as a combination of read (`r`), write (`w`), and execute (`x`) permissions for the owner, group, and others:

```bash
# View file permissions
ls -l file.txt
# Output: -rw-r--r-- 1 user group 2048 Apr 10 15:30 file.txt

# Change permissions
chmod u+x script.sh  # Add execute permission for user
chmod 755 script.sh  # Set rwx for user, rx for group and others
```

## Common Command Combinations

```bash
# Find and delete all .tmp files
find . -name "*.tmp" -delete

# Search for text in files and count occurrences
grep "Error" log.txt | wc -l

# Monitor the last 10 lines of a log file as it grows
tail -f -n 10 /var/log/syslog

# Find the largest files in a directory
du -h /home | sort -hr | head -10
```