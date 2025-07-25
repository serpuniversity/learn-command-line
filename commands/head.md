# `head`

> _"Just show me the beginning!"_

The `head` command shows you the first few lines of a file. Think of it as peeking at the top of a document - you get to see how it starts without having to read the whole thing. Perfect for checking file headers, previewing large files, or getting a quick sample of data.

<a href="#" target="_blank">
<img src="#" width="1000px">
</a>

## Name

`head` - display first lines of files

## Mnemonic

`head` shows the **head** (top/beginning) of a file.

## Syntax & Common Usage

The `head` command is simple - give it a file and it shows you the beginning.

For example:
```bash
head [options] [filename]
```

## Examples

### View first 10 lines (default)
The most basic use - just see the beginning of a file. Great for getting a quick preview without opening the entire file.
```bash
head myfile.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>

### View specific number of lines
Use `-n` to specify exactly how many lines you want to see. Perfect when you need more or fewer than the default 10 lines.
```bash
head -n 5 myfile.txt
head -n 20 logfile.log
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Quick check of multiple files
See the beginning of several files at once. Head will show which file each section comes from.
```bash
head file1.txt file2.txt file3.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Preview large data files
Perfect for checking CSV files, datasets, or any large file to see its structure before processing.
```bash
head -n 5 data.csv
head -n 3 users.json
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Check log files
Great for seeing the most recent entries in log files (if they're written from top to bottom).
```bash
head -n 20 /var/log/syslog
head error.log
```
<REPLACE_WITH_IMAGE_OR_GIF>

### View file headers and shebangs
Check the first line of scripts to see what interpreter they use (#!/bin/bash, #!/usr/bin/python, etc.).
```bash
head -n 1 script.sh
head -n 1 *.py
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Combine with other commands
Use head in pipes to limit output from other commands. Super useful for controlling how much data you see.
```bash
ls -la | head -n 5     # First 5 files in directory listing
ps aux | head -n 10    # First 10 running processes
```
<REPLACE_WITH_IMAGE_OR_GIF>

### View by bytes instead of lines
Use `-c` to see a specific number of characters/bytes instead of lines. Useful for binary files or precise data extraction.
```bash
head -c 100 file.txt   # First 100 characters
head -c 1K image.jpg   # First 1024 bytes
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Show all but last N lines
Use `-n -X` to show everything except the last X lines. Handy for removing file footers or signatures.
```bash
head -n -5 document.txt   # All lines except last 5
head -n -1 script.sh      # All lines except last line
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Save preview to another file
Redirect head's output to create a sample or preview file from a larger dataset.
```bash
head -n 1000 huge_data.csv > sample.csv
head -n 50 access.log > recent_entries.log
```
<REPLACE_WITH_IMAGE_OR_GIF>

## Command Quick Reference

| Command | What It Does | Example |
|---------|--------------|---------|
| `head file.txt` | Show first 10 lines | Default behavior |
| `head -n 5 file.txt` | Show first 5 lines | Custom line count |
| `head -n -3 file.txt` | All except last 3 lines | Exclude from end |
| `head -c 100 file.txt` | First 100 characters | By bytes, not lines |
| `head file1 file2` | First 10 lines of each file | Multiple files |
| `head *.log` | First 10 lines of all .log files | Wildcard matching |
| `command \| head` | First 10 lines of command output | Pipe usage |
| `head -n 20 \| tail -n 5` | Lines 16-20 | Combined with tail |

## Tips

### When to Use head
- **Large files**: Preview without opening huge files in editors
- **Log analysis**: Check recent entries (if logs grow from top)
- **Data exploration**: See structure of CSV, JSON, or other data files
- **Script debugging**: Check shebang lines and file headers
- **Command output control**: Limit verbose command output

### head vs Other Commands
- **head**: Shows the beginning of files
- **tail**: Shows the end of files  
- **cat**: Shows entire file content
- **less/more**: Interactive viewing of files
- **grep**: Shows lines matching patterns

### Common Use Cases
```bash
# Check what type of script this is
head -n 1 *.sh

# Preview a large dataset
head -n 5 sales_data.csv

# See recent log entries (if logs are ordered chronologically)
head -n 20 /var/log/messages

# Get first few results from a search
grep "error" logfile.txt | head -n 10
```

### Combining with tail for Specific Ranges
Get lines from the middle of a file:
```bash
# Get lines 15-20
head -n 20 file.txt | tail -n 6

# Get just line 50
head -n 50 file.txt | tail -n 1
```

### Working with Different File Types
- **Text files**: Default line-based viewing works great
- **CSV files**: Perfect for seeing headers and sample data
- **Log files**: Great for checking recent entries
- **Scripts**: Check interpreter and initial comments
- **Binary files**: Use `-c` option for byte-based viewing

### Performance Benefits
head is much faster than opening large files in editors because it only reads the beginning of the file, not the entire content.
