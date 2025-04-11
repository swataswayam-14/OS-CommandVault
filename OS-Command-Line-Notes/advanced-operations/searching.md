# Searching Files and Content

## Searching Within Files

### Windows (PowerShell)
```powershell
# Search for text in a specific file
Select-String cow farm_animals.txt

# Search across multiple files using wildcards
Select-String cow *.txt

# Case-insensitive search
Select-String -Pattern "COW" -CaseSensitive:$false farm_animals.txt
```

**Features of `Select-String`:**
- Outputs file name and line number
- Supports regular expressions for pattern matching
- Can be combined with other commands using pipelines

### Linux (Bash)
```bash
# Search for text in a specific file
grep cow farm_animals.txt

# Search across multiple files
grep cow *_animals.txt

# Case-insensitive search
grep -i COW farm_animals.txt

# Show line numbers in results
grep -n cow farm_animals.txt
```

## Searching Within Directories

### Windows (PowerShell)
```powershell
# Find all executable files in Program Files and subdirectories
ls 'C:\Program Files\' -Recurse -Filter *.exe

# Find all text files containing "important"
ls -Recurse -Filter *.txt | Select-String "important"
```

**Key Parameters:**
- `-Recurse`: Search subdirectories
- `-Filter`: Filter results by filename pattern

### Linux (Bash)
```bash
# Find all executable files in /usr/bin
find /usr/bin -name "*.sh"

# Find all text files modified in the last 7 days
find ~/Documents -name "*.txt" -mtime -7

# Find all files containing "important"
grep -r "important" ~/Documents
```

## Advanced Search Techniques

### Combining Search with Other Operations

**Windows (PowerShell):**
```powershell
# Find and copy all PDF files
ls -Recurse -Filter *.pdf | Copy-Item -Destination ~\PDFBackup\

# Count occurrences of a word across files
(Select-String "error" -Path .\logs\*.log).Count
```

**Linux (Bash):**
```bash
# Find and copy all PDF files
find ~/Documents -name "*.pdf" -exec cp {} ~/PDFBackup/ \;

# Count occurrences of a word across files
grep -r "error" ./logs/ | wc -l
```

## Search Decision Flowchart

```mermaid
flowchart TD
    A[Need to find something] --> B{What are you searching for?}
    B -- Text within files --> C{Which OS?}
    B -- Files by name/type --> D{Which OS?}
    
    C -- Windows --> E[Use Select-String]
    C -- Linux --> F[Use grep]
    
    D -- Windows --> G[Use ls -Recurse -Filter]
    D -- Linux --> H[Use find command]
    
    E --> I[Analyze results]
    F --> I
    G --> I
    H --> I
    
    I --> J{Need to process results?}
    J -- Yes --> K{Which OS?}
    J -- No --> L[Done]
    
    K -- Windows --> M[Use pipeline | to pass to another command]
    K -- Linux --> N[Use pipeline | or -exec with find]
```