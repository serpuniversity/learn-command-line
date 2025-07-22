# `cd`

> _"How do I get out of here?"_

The `cd` command changes the current working directory (folder), allowing you to move between directories (folders) on the filesystem.

# Click to watch the video 👇

<a href="https://www.youtube.com/watch?v=xn4IPic-VnY" target="_blank">
<img src="https://raw.githubusercontent.com/devinschumacher/uploads/refs/heads/main/images/cd-command-description-explanation-reference-examples-how-to-change-directories-in-terminal.jpg" width="1000px">
</a>

## Name

`cd` - change directory

## Mnemonic

`cd` stands for **c**hange **d**irectory.

## Options

- `cd -`: Change to the previous working directory

## Examples

### Move up one directory
```bash
cd ..
```
<img width="800" alt="Moving up one directory with cd .." target="_blank" src="https://github.com/serpuniversity/command-line/blob/main/images/cd-up-one.png" />

### Move up two directories
```bash
cd ../..
```
<img width="800" alt="Moving up two directories with cd ../.." target="_blank" src="https://github.com/serpuniversity/command-line/blob/main/images/cd-up-two.png" />

### Move to parent folder's sibling directory
```bash
cd ../another-directory
```
<img width="800" alt="Moving to parent folder's sibling directory with cd ../another-directory" target="_blank" src="https://github.com/serpuniversity/command-line/blob/main/images/cd-parent-sibling.png" />

### Switch back to previous directory
```bash
cd -
```
<img width="800" alt="Switching back to previous directory with cd -" target="_blank" src="https://github.com/serpuniversity/command-line/blob/main/images/cd-previous-directory.png" />

### Move the user's home directory
```bash
cd
cd ~
cd /Users/<username>
cd $HOME
```
<img width="800" alt="Moving to user's home directory with cd" target="_blank" src="https://github.com/serpuniversity/command-line/blob/main/images/cd-home.png" />

### Move directly to the filesystem's root directory
```bash
cd /
```
<img width="800" alt="Moving to filesystem's root directory with cd /" target="_blank" src="https://github.com/serpuniversity/command-line/blob/main/images/cd-root.png" />


### Move to a specific directory
```bash
cd ~/Desktop
cd [directoryName]
cd [directoryName/subDirectoryName]
```
<img width="800" alt="Moving to specific directory with cd ~/Desktop" target="_blank" src="https://github.com/serpuniversity/command-line/blob/main/images/cd-specific-directory.png" />

## Command Quick Reference

| Command | What It Does | Example |
|---------|--------------|---------|
| `cd` | Go to home directory | `cd` → `/Users/<username>` |
| `cd ~` | Go to home directory | `cd ~` → `/Users/<username>` |
| `cd ..` | Go up one level | From current directory to parent |
| `cd ../..` | Go up two levels | From current directory up two levels |
| `cd -` | Go back to previous directory | Switches between last two directories |
| `cd /` | Go to root directory | `cd /` → `/` |
| `cd ~/Desktop` | Go to Desktop | `cd ~/Desktop` → `~/Desktop` |
| `cd ../another-directory` | Go to sibling directory | From one folder to its sibling |


## Tips

### How to Handle Spaces in Directory Names
```bash
cd "My Documents"
# or
cd My\ Documents
```

<img width="800" alt="How to Handle Spaces in Directory Names with cd command" target="_blank" src="https://github.com/serpuniversity/command-line/blob/main/images/cd-with-spaces.png" />
