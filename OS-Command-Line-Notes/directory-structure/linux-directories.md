# Linux Directory Structure

## Filesystem Hierarchy

Unlike Windows with its drive letters, Linux uses a unified directory structure starting with a single root `/`:

```
/
├── bin/       # Essential command binaries
├── boot/      # Boot loader files
├── dev/       # Device files
├── etc/       # System configuration files
├── home/      # User home directories
├── lib/       # Essential shared libraries
├── media/     # Mount points for removable media
├── mnt/       # Temporary mount points
├── opt/       # Optional application software
├── proc/      # Virtual filesystem for system information
├── root/      # Home directory for the root user
├── run/       # Run-time variable data
├── sbin/      # System binaries
├── srv/       # Data for services provided by the system
├── sys/       # Virtual filesystem for system information
├── tmp/       # Temporary files
├── usr/       # Secondary hierarchy (user programs)
└── var/       # Variable data (logs, etc.)
```

## Key Directories Explained

| Directory | Purpose |
|-----------|---------|
| `/bin` | Stores essential program binaries (executables) |
| `/etc` | System configuration files |
| `/home` | Personal directories for users |
| `/proc` | Virtual filesystem showing running processes |
| `/usr` | User installed software and resources |
| `/var` | Variable data like logs and temporary files |

## User Home Directory

Each user has their own directory under `/home/[username]/` containing:

```
/home/[username]/
├── Desktop/       # User's desktop files
├── Documents/     # User's documents
├── Downloads/     # Downloaded files
├── Pictures/      # User's pictures
├── Music/         # User's music files
└── Videos/        # User's video files
```

## Path Types

1. **Absolute Path**: Starts from the root directory
   - Example: `/home/Swayam/Desktop/file.txt`

2. **Relative Path**: Based on your current directory
   - Example: If you're in `/home/Swayam/`, the relative path to Desktop would be just `Desktop/`

3. **Home Directory Shortcut**: The tilde (`~`) represents your home directory
   - Example: `~/Desktop` is equivalent to `/home/[username]/Desktop`

## Command Line Interface

Linux primarily uses various shells as command-line interfaces, with **Bash** being the most common.

![Linux Directory Structure](../assets/diagrams/linux-directory-structure.svg)