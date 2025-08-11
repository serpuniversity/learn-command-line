---
title: How to use the `cat` terminal command
tags:
  - command line
  - linux
---

# `cat`

> _"What's in this file?"_

The `cat` command shows you what's inside files. 

Think of it as opening a file and reading it, but in the terminal. It displays the contents of text files right on your screen, making it perfect for quickly peeking at files without opening an editor.

<a href="#" target="_blank">
<img src="#" width="1000px">
</a>

## Name

`cat` - concatenate and display files

## Mnemonic

`cat` stands for con**cat**enate (to link things together in a chain).

## Syntax & Common Usage

The `cat` command is simple - just give it a filename and it shows you what's inside.

For example:
```bash
cat [options] [filename]
```

## Examples

### View a file's contents
The most basic use - just see what's inside a text file. Perfect for quickly checking config files, scripts, or any text document.
```bash
cat myfile.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>

### View multiple files at once
Shows the contents of several files one after another, like reading multiple documents in sequence.
```bash
cat file1.txt file2.txt file3.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>

### View system files
Great for checking configuration files, logs, or system information without opening an editor.
```bash
cat /etc/hosts
cat /var/log/syslog
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Create a new file
Type `cat > filename` then start typing. When you're done, press Ctrl+D to save. It's a quick way to create small files.
```bash
cat > newfile.txt
# Type your content here
# Press Ctrl+D when done
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Append to an existing file
Add content to the end of a file without overwriting what's already there. The `>>` means "append to."
```bash
cat >> existing_file.txt
# Type additional content
# Press Ctrl+D when done
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Copy file contents to another file
Use `>` to redirect the output to a new file. This copies the contents of one file into another.
```bash
cat source.txt > destination.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Combine multiple files into one
Merge several files together into a single file. Super useful for combining log files or data files.
```bash
cat file1.txt file2.txt file3.txt > combined.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Show line numbers
The `-n` option adds line numbers to each line. Helpful for referencing specific lines or debugging code.
```bash
cat -n script.py
```
<REPLACE_WITH_IMAGE_OR_GIF>

### View files with less scrolling
For long files, combine cat with `less` to scroll through the content page by page instead of having it all zoom past.
```bash
cat longfile.txt | less
```
<REPLACE_WITH_IMAGE_OR_GIF>

## Command Quick Reference

| Command | What It Does | Example |
|---------|--------------|---------|
| `cat file.txt` | View file contents | Shows what's in the file |
| `cat file1 file2` | View multiple files | Shows both files in sequence |
| `cat > newfile.txt` | Create new file | Type content, Ctrl+D to save |
| `cat >> file.txt` | Append to file | Add content to end of file |
| `cat file.txt > copy.txt` | Copy file | Makes a copy of the file |
| `cat *.txt` | View all .txt files | Shows all text files |
| `cat -n file.txt` | Show with line numbers | Adds numbers to each line |
| `cat file.txt \| less` | Paginated viewing | Scroll through long files |

## Tips

### When to Use cat vs Other Commands
- **cat**: Quick peek at short files, combining files, creating small files
- **less** or **more**: Better for long files you want to scroll through
- **head**: Just see the first few lines
- **tail**: Just see the last few lines

### Great for Configuration Files
cat is perfect for checking config files:
```bash
cat ~/.bashrc       # Your shell configuration
cat /etc/passwd     # User accounts
cat /etc/hosts      # Network host mappings
```

### Creating Quick Files
Instead of opening a text editor for small files:
```bash
cat > quick_note.txt
This is a quick note
I can type multiple lines
Ctrl+D saves and exits
```

### Combining with Other Commands
cat works great with pipes:
```bash
cat access.log | grep "ERROR"    # Find errors in log files
cat data.txt | sort               # Show sorted file contents
cat config.txt | head -10        # First 10 lines of a file
```

### Be Careful with Binary Files
Don't use cat on binary files (images, executables, etc.) - it'll show garbage characters and might mess up your terminal. Stick to text files!

### The "Useless Use of Cat" Debate
Some people say `cat file.txt | grep something` is wasteful compared to `grep something file.txt`. They're technically right, but cat is often clearer to read and understand, especially in examples and tutorials.
