# `pwd`

> _"Where am I?"_

The `pwd` command tells you exactly where you are in the filesystem. It's like having a GPS for your terminal - it shows you the full path from the root directory to wherever you currently are.

<a href="#" target="_blank">
<img src="#" width="1000px">
</a>

## Name

`pwd` - print working directory

## Mnemonic

`pwd` stands for **p**rint **w**orking **d**irectory.

## Syntax & Common Usage

The `pwd` command is super simple - you just type it and it tells you where you are.

For example:
```bash
pwd
```

## Examples

### Show current directory
The most basic use - just see where you are right now. It shows the complete path from the root (/) to your current location.
```bash
pwd
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Use pwd when you're lost
If you've been cd-ing around and don't remember where you ended up, pwd is your friend. It's like asking "Where am I?" in the terminal.
```bash
pwd
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Combine with cd to navigate
Use pwd before and after changing directories to see where you were and where you are now.
```bash
pwd
cd ~/Documents
pwd
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Store current directory in a variable
Capture your current location so you can remember it or come back to it later in a script.
```bash
current_location=$(pwd)
echo "I was in: $current_location"
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Use pwd in scripts
Great for scripts that need to know where they're running from or need to work with absolute paths.
```bash
#!/bin/bash
echo "This script is running from: $(pwd)"
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Check if you're in the right directory
Before running important commands, use pwd to make sure you're in the correct folder.
```bash
pwd
# Make sure you're in the right place before running commands
ls -la
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Navigate back to a saved location
Combine with cd to save your current location and return to it later.
```bash
original_dir=$(pwd)
cd /tmp
# do some work in /tmp
cd "$original_dir"  # back to where you started
pwd  # confirm you're back
```
<REPLACE_WITH_IMAGE_OR_GIF>

## Command Quick Reference

| Command | What It Does | Example Output |
|---------|--------------|----------------|
| `pwd` | Show current directory | `/home/username/Documents` |
| `current=$(pwd)` | Save location in variable | Stores path for later use |
| `pwd && ls` | Show location then list files | Shows where you are, then what's there |
| `echo $(pwd)` | Print current directory in text | `Current directory: /home/user` |

## Tips

### When to Use pwd
- **When you're lost**: After lots of cd commands and don't know where you are
- **Before dangerous commands**: Like `rm *` - make sure you're in the right place!
- **In scripts**: When your script needs to know its working directory
- **For debugging**: To see exactly where commands are running from

### Understanding the Output
The output always starts with `/` (the root directory) and shows the complete path:
- `/` = root directory (top level)
- `/home` = inside the home directory
- `/home/username` = inside your user directory
- `/home/username/Documents` = inside your Documents folder

### pwd vs $PWD
There's also a built-in variable `$PWD` that contains the same info:
```bash
echo $PWD  # Same as pwd, but as a variable
```

### The "Working Directory" Concept
Your "working directory" (or "current directory") is where the terminal thinks you are. When you use relative paths like `./file.txt` or `../folder`, they're relative to this location that pwd shows you.
