# `echo`

> _"Say something!"_

The `echo` command prints text to the screen. Think of it as the computer's way of "saying" something - you give it text, and it displays it in the terminal. It's perfect for showing messages, displaying variables, or adding output to scripts.

<a href="#" target="_blank">
<img src="#" width="1000px">
</a>

## Name

`echo` - display a line of text

## Mnemonic

`echo` means to repeat or **echo** back what you give it.

## Syntax & Common Usage

The `echo` command is simple - just tell it what to say and it'll display it.

For example:
```bash
echo [options] [text]
```

## Examples

### Display simple text
The most basic use - just print some text to the screen. Great for messages, reminders, or testing.
```bash
echo "Hello, World!"
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Display without quotes
You can skip quotes for simple text without spaces or special characters.
```bash
echo Hello
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Display variables
Show the value stored in variables. The `$` tells echo to use the variable's value, not its name.
```bash
echo "Welcome, $USER!"
echo "You are in: $PWD"
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Create files with content
Use `>` to save echo's output to a file instead of displaying it. Perfect for quickly creating files with content.
```bash
echo "This is my first line" > newfile.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Append to existing files
Use `>>` to add content to the end of an existing file without overwriting what's already there.
```bash
echo "This gets added to the end" >> existing_file.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Display multiple lines
Use `-e` with `\n` to create line breaks. Great for formatting messages or creating structured output.
```bash
echo -e "First line\nSecond line\nThird line"
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Print without newline
Use `-n` to keep the cursor on the same line after printing. Useful for prompts or when building output piece by piece.
```bash
echo -n "Enter your name: "
# Cursor stays here for user input
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Display with tabs
Use `-e` with `\t` to add tab spacing. Perfect for creating simple tables or aligned text.
```bash
echo -e "Name:\tJohn\nAge:\t25\nCity:\tNew York"
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Show command output
Combine echo with command substitution to display both text and command results.
```bash
echo "Today is: $(date)"
echo "Current directory: $(pwd)"
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Test dangerous commands safely
Before running destructive commands, use echo to see what would happen without actually doing it.
```bash
echo rm *.txt  # Shows what files would be deleted
# Only run the real command if the output looks right
```
<REPLACE_WITH_IMAGE_OR_GIF>

## Command Quick Reference

| Command | What It Does | Example |
|---------|--------------|---------|
| `echo "text"` | Display text | `echo "Hello World"` |
| `echo $VARIABLE` | Display variable value | `echo $HOME` |
| `echo text > file` | Create file with content | `echo "data" > file.txt` |
| `echo text >> file` | Append to file | `echo "more" >> file.txt` |
| `echo -n "text"` | No newline at end | Keeps cursor on same line |
| `echo -e "line1\nline2"` | Enable escape sequences | Creates multiple lines |
| `echo -e "word\tword"` | Add tabs | Creates tabbed spacing |
| `echo $(command)` | Show command output | `echo $(date)` |

## Tips

### Quotes Matter
- **No quotes**: `echo hello world` works for simple text
- **Double quotes**: `echo "hello $USER"` - variables are expanded
- **Single quotes**: `echo 'hello $USER'` - variables are treated as literal text

### Common Escape Sequences (use with -e)
- `\n` - New line
- `\t` - Tab
- `\r` - Carriage return
- `\b` - Backspace
- `\\` - Literal backslash

### Creating Quick Files
```bash
echo "#!/bin/bash" > script.sh          # Start a shell script
echo "TODO: Fix the bug" > notes.txt    # Quick note-taking
echo "127.0.0.1 localhost" > hosts.txt  # Config file entries
```

### Debugging Scripts
Use echo to see what's happening in your scripts:
```bash
echo "Starting backup process..."
echo "Backing up: $backup_dir"
echo "Destination: $dest_dir"
```

### Environment Variables
Echo is great for checking system information:
```bash
echo $PATH      # Your system PATH
echo $HOME      # Your home directory
echo $SHELL     # Your current shell
echo $USER      # Your username
```

### Building Complex Output
Combine multiple techniques:
```bash
echo -e "System Report\n============="
echo "User: $USER"
echo "Date: $(date)"
echo -e "Disk Usage:\n$(df -h /)"
```

### Safety First
Always test destructive commands with echo first:
```bash
echo rm -rf /old_backups/*    # Check what would be deleted
echo mv *.log /archive/       # Check what would be moved
```
