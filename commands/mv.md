# `mv`

> _"How do I move that?"_

The `mv` command moves things. It can move files or folders from one location to another. It can also rename them (that's kind of like moving them... right? ...sorta?).

<a href="#" target="_blank">
<img src="#" width="1000px">
</a>

## Name

`mv` - move (and/or rename) files and directories

## Mnemonic

`mv` stands for **m**o**v**e.

## Syntax & Common Usage

You'll typically use the `mv` command with the same syntax you're used to for navigating between directories in your filesystem (ie: `..` or `../..` etc.)

For example:
```bash
`mv [nameOfThingToMove] [destinationToMoveItTo]`
```

## Examples

### Rename a file
```bash
mv oldname.txt newname.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Move a file to another directory
```bash
mv document.txt ~/Documents/
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Move and rename a file in one command
```bash
mv report.txt ~/Documents/final_report.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Move multiple files to a directory

If you want to move multiple files at a time, it's simple. Simply use the move command and put a space in between each file that you want to move and whatever the last thing in your command, that is where all of them will move to.

```bash
mv file1.txt file2.txt file3.txt ~/Documents/
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Move files with wildcards
```bash
mv *.txt ~/Documents/
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Rename a directory
```bash
mv old_folder new_folder
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Move a directory
```bash
mv ~/Desktop/project ~/Documents/
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Interactive mode (prompt before overwriting)
```bash
mv -i source.txt destination.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Verbose mode (show what's happening)
```bash
mv -v *.pdf ~/Documents/
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Create backup before overwriting
```bash
mv -b important.txt ~/backup/important.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>

## Command Quick Reference

| Command | What It Does | Example |
|---------|--------------|---------|
| `mv file1 file2` | Rename file1 to file2 | `mv report.txt final_report.txt` |
| `mv file dir/` | Move file to directory | `mv photo.jpg ~/Pictures/` |
| `mv file dir/newname` | Move and rename | `mv temp.txt ~/Documents/notes.txt` |
| `mv *.txt dir/` | Move all .txt files | `mv *.txt ~/Documents/` |
| `mv -i file1 file2` | Interactive (prompt before overwrite) | `mv -i config.txt backup.txt` |
| `mv -f file1 file2` | Force overwrite | `mv -f new.txt old.txt` |
| `mv -n file1 file2` | Never overwrite | `mv -n draft.txt final.txt` |
| `mv -v file dir/` | Verbose output | `mv -v *.log ~/logs/` |
| `mv -b file1 file2` | Create backup | `mv -b data.txt data_old.txt` |
| `mv dir1 dir2` | Rename/move directory | `mv project_old project_new` |

## Tips

### How to Handle Spaces in File/Directory Names
```bash
mv "My Document.txt" "Final Document.txt"
# or
mv My\ Document.txt Final\ Document.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>

