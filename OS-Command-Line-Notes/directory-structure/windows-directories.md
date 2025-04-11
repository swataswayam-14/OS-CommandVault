# Windows Directory Structure

## Root Directory Structure

The Windows file system is organized in drives, with each drive having its own root directory:

```
C:\     # Main system drive (root directory for C drive)
X:\     # Example of another drive (root directory for X drive)
```

## Key System Directories

Windows has several important system directories:

| Directory | Purpose |
|-----------|---------|
| `C:\Windows` | Contains the Windows operating system files |
| `C:\Program Files` | Contains 64-bit program installations |
| `C:\Program Files (x86)` | Contains 32-bit program installations |
| `C:\ProgramData` | Holds data for programs installed in Program Files |
| `C:\Users` | Home directories for all users on the system |

## User Directory Structure

Each user has their own directory under `C:\Users\[Username]` containing:

```
C:\Users\[Username]\
├── Desktop\       # User's desktop files
├── Documents\     # User's documents
├── Downloads\     # Downloaded files
├── Pictures\      # User's pictures
├── Music\         # User's music files
├── Videos\        # User's video files
└── AppData\       # Application data (largely hidden)
```

## Path Types

1. **Absolute Path**: Starts from the root directory
   - Example: `C:\Users\Swayam\Desktop\file.txt`

2. **Relative Path**: Based on your current directory
   - Example: If you're in `C:\Users\Swayam\`, the relative path to Desktop would be just `Desktop\`

## Command Line Interfaces

Windows provides multiple command-line interfaces:
- **Command Prompt** (`cmd.exe`): Traditional Windows command line
- **PowerShell** (`powershell.exe`): Advanced command shell and scripting language

![Windows Directory Structure](../assets/diagrams/windows-directory-structure.svg)