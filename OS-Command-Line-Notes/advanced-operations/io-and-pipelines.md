# I/O Streams and Pipelines

## Understanding I/O Streams

Both Windows and Linux use three standard I/O streams:

| Stream | Number | Description |
|--------|--------|-------------|
| stdin | 0 | Standard input (keyboard by default) |
| stdout | 1 | Standard output (screen by default) |
| stderr | 2 | Standard error (screen by default) |

## Redirection Operators

### Output Redirection

#### Windows (PowerShell)
```powershell
# Redirect output to a file (overwrite)
echo woof > dog.txt

# Append output to a file
echo woof >> dog.txt
```

#### Linux (Bash)
```bash
# Redirect output to a file (overwrite)
echo woof > dog.txt

# Append output to a file
echo woof >> dog.txt
```

### Input Redirection

#### Windows (PowerShell)
```powershell
# Less commonly used in PowerShell
Get-Content < input_file.txt
```

#### Linux (Bash)
```bash
# Take input from a file instead of keyboard
cat < file_input.txt
```

### Error Redirection

#### Windows (PowerShell)
```powershell
# Redirect error messages to a file
rm secure_file 2> errors.txt

# Discard error messages
rm secure_file 2> $null
```

#### Linux (Bash)
```bash
# Redirect error messages to a file
ls /dir/fake_dir 2> error_output.txt

# Discard error messages
less /var/log/syslog 2> /dev/null
```

## Pipelines

Pipelines allow you to connect the output of one command to the input of another.

### Windows (PowerShell)
```powershell
# Find words containing "st" in a file
cat words.txt | Select-String st

# Find words with "st" and save to a file
cat words.txt | Select-String st > st_words.txt

# List processes and filter by name
Get-Process | Where-Object { $_.Name -like "*chrome*" }
```

### Linux (Bash)
```bash
# Find subdirectories in /etc containing "bluetooth"
ls -la /etc | grep bluetooth

# Count number of files in current directory
ls | wc -l

# Find largest files in directory
du -h | sort -hr | head -5
```

## I/O Stream Visual Model

```mermaid
graph LR
    A[Keyboard] -->|stdin| B[Command/Process]
    B -->|stdout| C[Screen]
    B -->|stderr| D[Screen]
    
    E[File] -.->|stdin < file| B
    B -.->|stdout > file| F[Output File]
    B -.->|stderr 2> file| G[Error File]
    
    H[Command1] -->|stdout| I[pipe |]
    I -->|stdin| J[Command2]
```

## Common Pipeline Patterns

### Data Processing Pipelines

**Windows:**
```powershell
# List services, filter, sort, format
Get-Service | Where-Object Status -eq "Running" | Sort-Object DisplayName | Format-Table -Property DisplayName, Status
```

**Linux:**
```bash
# Find largest directories
du -h /home | sort -hr | head -10

# Extract data from a log file
cat access.log | grep "ERROR" | cut -d' ' -f1,2 | sort | uniq -c
```