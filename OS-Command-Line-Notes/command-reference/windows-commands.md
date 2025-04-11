# Windows Command Reference

## Command Prompt vs PowerShell

Windows offers two main command-line interfaces:

1. **Command Prompt (cmd.exe)**: Traditional MS-DOS-style command processor
2. **PowerShell**: Modern command shell with scripting capabilities

PowerShell commands (called cmdlets) follow a `Verb-Noun` pattern and are more consistent than Command Prompt commands.

## Command Aliases

PowerShell provides aliases to help users familiar with other command lines:

```powershell
# View all aliases
Get-Alias

# Check alias for a specific command
Get-Alias ls

# Output: CommandType Name Version Source
#          ---------- ---- ------- ------
#          Alias      ls   -> Get-ChildItem
```

## Common PowerShell Commands

| PowerShell Cmdlet | Alias | Description |
|-------------------|-------|-------------|
| `Get-ChildItem` | `ls`, `dir` | List directory contents |
| `Set-Location` | `cd` | Change directory |
| `Get-Content` | `cat`, `type` | Display file contents |
| `Copy-Item` | `cp`, `copy` | Copy files/directories |
| `Move-Item` | `mv`, `move` | Move/rename files/directories |
| `Remove-Item` | `rm`, `del` | Delete files/directories |
| `Write-Output` | `echo` | Display text on screen |
| `Get-Help` | `help` | Display help information |
| `Clear-Host` | `cls`, `clear` | Clear the screen |
| `Select-String` | `grep` (Linux equivalent) | Search for text |
| `New-Item` | `mkdir` | Create new item |

## PowerShell vs CMD Commands

| Task | PowerShell | Command Prompt |
|------|------------|----------------|
| List directory | `Get-ChildItem` or `ls` | `dir` |
| Change directory | `Set-Location` or `cd` | `cd` |
| Create directory | `New-Item -ItemType Directory` or `mkdir` | `mkdir` |
| Display file | `Get-Content` or `cat` | `type` |
| Copy file | `Copy-Item` or `cp` | `copy` |
| Move file | `Move-Item` or `mv` | `move` |
| Delete file | `Remove-Item` or `rm` | `del` |
| Get help | `Get-Help` | `[command] /?` |

## Getting Help

```powershell
# Get basic help for a command
Get-Help Get-ChildItem

# Get detailed help with examples
Get-Help Get-ChildItem -Full

# Get examples only
Get-Help Get-ChildItem -Examples
```

In Command Prompt:
```cmd
dir /?
```

## Parameter Types

PowerShell uses various parameter types:

1. **Positional Parameters**:
   ```powershell
   Copy-Item source.txt destination.txt
   ```

2. **Named Parameters**:
   ```powershell
   Copy-Item -Path source.txt -Destination destination.txt
   ```

3. **Switch Parameters**:
   ```powershell
   Copy-Item source.txt destination.txt -Recurse
   ```

4. **Common Parameters** (available to all cmdlets):
   ```powershell
   Get-ChildItem -Verbose
   ```