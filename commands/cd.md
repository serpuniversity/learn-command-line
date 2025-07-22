# `cd`

> **"How do I get out of here?"**

The `cd` command changes the current working directory (folder), allowing you to move between directories (folders) on the filesystem.

## Name

`cd` - change directory

## Mnemonic

`cd` stands for **c**hange **d**irectory.

Think _"how do i get out of here?"_

## Options

- `cd -`: Change to the previous working directory

## Examples

### Move up one directory
```bash
cd ..
```
<INSERT_TERMINAL_RECORDING_OR_GIF_HERE>

### Move up two directories
```bash
cd ../..
```
<INSERT_TERMINAL_RECORDING_OR_GIF_HERE>

### Move to parent folder's sibling directory
```bash
cd ../another-directory
```
<INSERT_TERMINAL_RECORDING_OR_GIF_HERE>

### Switch back to previously directory
```bash
cd -
```
<INSERT_TERMINAL_RECORDING_OR_GIF_HERE>

### Move the user's home directory
```bash
cd
cd ~
cd $HOME
```
<INSERT_TERMINAL_RECORDING_OR_GIF_HERE>

### Move directly to the filesystem's root directory
```bash
cd /
```
<INSERT_TERMINAL_RECORDING_OR_GIF_HERE>

### Move to a specific directory
```bash
cd ~/Desktop
cd [directoryName]
cd [directoryName/subDirectoryName]
```
<INSERT_TERMINAL_RECORDING_OR_GIF_HERE>

## Command Quick Reference

| Command | What It Does | Example |
|---------|--------------|---------|
| `cd` | Go to home directory | `cd` → `/home/username` |
| `cd ~` | Go to home directory | `cd ~` → `/home/username` |
| `cd ..` | Go up one level | From `/home/user/docs` → `/home/user` |
| `cd ../..` | Go up two levels | From `/home/user/docs/work` → `/home/user` |
| `cd -` | Go back to previous directory | Toggles between last two directories |
| `cd /` | Go to root directory | `cd /` → `/` |
| `cd ~/Desktop` | Go to Desktop | `cd ~/Desktop` → `/home/username/Desktop` |
| `cd ../sibling` | Go to sibling directory | From `/docs/folder1` → `/docs/folder2` |


## Tips

### How to Handle Spaces in Directory Names
```bash
cd "My Documents"
# or
cd My\ Documents
```
<INSERT_TERMINAL_RECORDING_OR_GIF_HERE>


