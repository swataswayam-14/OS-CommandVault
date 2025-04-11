# File Operations

## Copying Files and Directories

### Windows (PowerShell)
```powershell
# Copy a single file
cp mycoolfile.txt C:\Users\Swayam\Desktop

# Copy using wildcard patterns
cp *.jpg ~\Desktop  # Copies all jpg files to Desktop

# Copy directory (without contents)
cp 'Bird Pictures' ~\Desktop

# Copy directory with contents
cp 'Bird Pictures' ~\Desktop -Recurse -Verbose
```

**Parameters:**
- `-Recurse`: Include subdirectories and their contents
- `-Verbose`: Show detailed information about the copying process

### Linux (Bash)
```bash
# Copy a single file
cp my_cool_file.txt ~/Desktop

# Copy using wildcard patterns
cp *.png ~/Desktop  # Copies all png files to Desktop

# Copy directory with contents
cp -r 'Cat Pictures' ~/Desktop
```

**Parameters:**
- `-r`: Recursive copy (includes subdirectories and their contents)

## Moving and Renaming Files

### Windows (PowerShell)
```powershell
# Rename a file
mv .\blue.txt yellow.txt

# Move a file to another location
mv .\yellow.txt ~\Documents

# Move multiple files using wildcards
mv *_document.txt ~\Documents
```

### Linux (Bash)
```bash
# Rename a file
mv red_document.txt blue_document.txt

# Move a file to another location
mv blue_document.txt ~/Documents

# Move multiple files using wildcards
mv *_document.txt ~/Desktop
```

## Removing Files and Directories

> ⚠️ **Warning**: The `rm` command permanently deletes files and doesn't use the recycle bin/trash!

### Windows (PowerShell)
```powershell
# Remove a file
rm ~\text1.txt
# OR
remove ~\text1.txt

# Force removal of protected file
rm imp_file -Force

# Remove directory (prompts for confirmation)
rm ~\misc_folder

# Remove directory without confirmation
rm ~\misc_folder -Recurse
```

### Linux (Bash)
```bash
# Remove a file
rm text1.txt

# Remove directory and contents
rm -r misc_folder
```

## File Operation Workflows

### Copy Operation
```mermaid
flowchart TD
    A[Select Source File(s)] --> B{Single File or Directory?}
    B -- Single File --> C[cp file destination]
    B -- Directory --> D{Windows or Linux?}
    D -- Windows --> E[cp directory destination -Recurse]
    D -- Linux --> F[cp -r directory destination]
    C --> G[File Copied]
    E --> G
    F --> G
```

### Move Operation
```mermaid
flowchart TD
    A[Select Source File(s)] --> B{Rename or Move?}
    B -- Rename --> C[mv oldname newname]
    B -- Move --> D[mv source destination]
    C --> E[Operation Complete]
    D --> E
```