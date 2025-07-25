# `du`

> _"How big is this thing anyway?"_

The `du` command shows you the disk usage (file sizes) of files and directories. Think of it as your digital measuring tape for finding out how much space stuff is taking up on your computer.

<a href="#" target="_blank">
<img src="#" width="1000px">
</a>

## Name

`du` - display directory space usage

## Mnemonic

`du` stands for **d**isk **u**sage.

## Syntax & Common Usage

You'll typically use the `du` command to check how much space files and folders are using:

```bash
du [options] [directory/file]
```

## Examples

### Check current directory size
```bash
du
```
This shows the size of the current directory and all its subdirectories. The numbers might look weird because they're in "blocks" (usually 1024 bytes each) - not very human-friendly!

<REPLACE_WITH_IMAGE_OR_GIF>

### Check directory size in human-readable format
```bash
du -h
```
The `-h` flag makes the output "human-readable" - instead of seeing weird numbers like "2048", you'll see "2.0M" for 2 megabytes. Much better!

<REPLACE_WITH_IMAGE_OR_GIF>

### Get just the total size (summary)
```bash
du -sh Documents/
```
The `-s` flag gives you just the summary - the total size of the Documents folder without showing all the subdirectories inside it. Perfect when you just want the bottom line.

<REPLACE_WITH_IMAGE_OR_GIF>

### Check size of a specific directory
```bash
du -h ~/Downloads
```
This shows the size of your Downloads folder and all its subfolders in human-readable format. Great for seeing what's eating up your storage!

<REPLACE_WITH_IMAGE_OR_GIF>

### Show all files and directories (not just directories)
```bash
du -ah ~/Documents
```
The `-a` flag shows EVERYTHING - all files AND directories. Usually `du` only shows directories, but sometimes you want to see individual file sizes too.

<REPLACE_WITH_IMAGE_OR_GIF>

### Limit how deep it looks
```bash
du -h --max-depth=1 ~/
```
This only looks 1 level deep in your home directory. Super useful when you have lots of nested folders and just want to see the main folders without getting overwhelmed.

<REPLACE_WITH_IMAGE_OR_GIF>

### Show total at the bottom
```bash
du -ch ~/Documents
```
The `-c` flag adds a "total" line at the bottom. Handy when you're checking multiple directories and want to see the grand total.

<REPLACE_WITH_IMAGE_OR_GIF>

### Find the biggest directories
```bash
du -h ~/Documents | sort -h
```
This pipes the output to `sort -h` to show directories from smallest to largest. Perfect for finding what's taking up the most space!

<REPLACE_WITH_IMAGE_OR_GIF>

### Check multiple directories at once
```bash
du -sh Downloads/ Documents/ Pictures/
```
You can check multiple directories at once by listing them all. Each gets its own summary line - great for comparing folder sizes.

<REPLACE_WITH_IMAGE_OR_GIF>

### Exclude certain file types
```bash
du -h --exclude="*.mp4" ~/Videos
```
The `--exclude` option lets you ignore certain file types. This example ignores all .mp4 files when calculating the size of your Videos folder.

<REPLACE_WITH_IMAGE_OR_GIF>

## Command Quick Reference

| Command | What It Does | Example |
|---------|--------------|---------|
| `du` | Show directory sizes in blocks | `du ~/Documents` |
| `du -h` | Human-readable sizes (KB, MB, GB) | `du -h ~/Downloads` |
| `du -s` | Summary only (no subdirectories) | `du -s ~/Pictures` |
| `du -sh` | Human-readable summary | `du -sh ~/Videos` |
| `du -a` | Show all files, not just directories | `du -ah ~/Documents` |
| `du -c` | Show grand total at bottom | `du -ch ~/Downloads` |
| `du --max-depth=1` | Limit directory depth | `du -h --max-depth=1 ~/` |
| `du -h \| sort -h` | Sort by size (smallest to largest) | `du -h ~/Documents \| sort -h` |
| `du --exclude="*.ext"` | Exclude certain file types | `du -h --exclude="*.log" /var` |

## Tips

### Why use du instead of ls?
When you do `ls -l` on a directory, it shows 4096 bytes no matter how big the directory actually is. That's just the directory's metadata! `du` shows you the REAL size of everything inside.

### Finding space hogs quickly
```bash
du -h --max-depth=1 / | sort -h | tail -5
```
This finds the 5 biggest directories on your entire system. Super useful for cleaning up disk space!

### Common size units
- **K** = Kilobytes (thousands of bytes)
- **M** = Megabytes (millions of bytes)  
- **G** = Gigabytes (billions of bytes)
- **T** = Terabytes (trillions of bytes)
