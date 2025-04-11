# Viewing File Contents

## Displaying Complete File Contents

### Windows (PowerShell)
```powershell
# Display entire file content
cat .\imp_doc.txt
```

### Linux (Bash)
```bash
# Display entire file content
cat imp_doc.txt
```

> 💡 **Note**: `cat` stands for "concatenate" - it can join and display multiple files at once.

## Paging Through Large Files

### Windows (PowerShell)
```powershell
# View file with pagination
more .\large_doc.txt
```

**Navigation controls:**
- `Enter`: Advance by one line
- `Space`: Advance by one page
- `q`: Quit and return to shell

### Linux (Bash)
```bash
# View file with advanced pagination
less large_doc.txt
```

**Navigation controls in `less`:**
- `↑` / `↓`: Move up/down one line
- `Page Up` / `Page Down`: Move up/down one page
- `g`: Go to beginning of file
- `G`: Go to end of file
- `/word_search`: Search for text (example: `/mango`)
- `q`: Quit and return to shell

## Viewing Parts of Files

### Windows (PowerShell)
```powershell
# View first 10 lines
cat fruits.txt -Head 10

# View last 10 lines
cat fruits.txt -Tail 10
```

### Linux (Bash)
```bash
# View first 10 lines
head fruits.txt

# View last 10 lines
tail fruits.txt

# View specific number of lines
head -n 5 fruits.txt  # First 5 lines
tail -n 15 fruits.txt  # Last 15 lines
```