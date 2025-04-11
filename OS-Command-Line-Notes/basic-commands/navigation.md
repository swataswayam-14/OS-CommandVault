# Command Line Navigation

## Checking Current Location

### Windows (PowerShell)
```powershell
# Display current directory
pwd
```

### Linux (Bash)
```bash
# Display current directory
pwd
# Example output: /home/swayam/desktop
```

## Listing Directory Contents

### Windows (PowerShell)
```powershell
# List contents of current directory
ls

# List contents of specific directory
ls C:\

# Get detailed help for ls command
Get-Help ls

# Get full help documentation
Get-Help ls -full

# Show hidden files
ls -Force C:\
```

### Linux (Bash)
```bash
# List contents of current directory
ls

# List contents of root directory
ls /

# Show manual for ls command
man ls

# Long format listing (permissions, size, date)
ls -l

# Show all files including hidden ones
ls -la

# Show only hidden files
ls -a
```

## Changing Directories

### Windows (PowerShell)
```powershell
# Move to parent directory
cd ../

# Move to specific directory
cd ~\Desktop

# Move to absolute path
cd C:\Users\Swayam\Documents
```

### Linux (Bash)
```bash
# Move to parent directory
cd ../

# Move to desktop directory (relative to home)
cd ~/desktop

# Move to a directory relative to current location
cd ../documents

# Move to absolute path
cd /home/swayam/documents
```

## Tab Completion

### Windows (PowerShell)
Press Tab key to cycle through available options.

### Linux (Bash)
Press Tab key to:
- Complete a unique match immediately
- Show all possible options if multiple matches exist

## Creating Directories

### Windows (PowerShell)
```powershell
# Create a simple directory
mkdir my_cool_folder

# Create directory with spaces in name
mkdir "my cool folder"

# Alternative syntax with backticks
mkdir my`cool`folder
```

### Linux (Bash)
```bash
# Create a simple directory
mkdir my_cool_folder

# Create directory with spaces in name
mkdir 'my cool folder'

# Alternative with escape characters
mkdir my\ cool\ folder
```

## Command History

### Both Windows & Linux
```
# Show command history
history

# Search through command history
# Press Ctrl+R and type search term
```

**Navigation Workflow**
