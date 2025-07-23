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
mv [nameOfThingToMove] [destinationToMoveItTo]
```

## Examples

### Rename a file
This changes the name of "oldname.txt" to "newname.txt" - the file stays in the same location, just gets a new name.
```bash
mv oldname.txt newname.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Move a file to another directory
This takes "document.txt" from wherever you currently are and moves it into your Documents folder. The file keeps the same name, just changes location.
```bash
mv document.txt ~/Documents/
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Move and rename a file in one command
This does two things at once: moves "report.txt" to the Documents folder AND renames it to "final_report.txt". Pretty handy!
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
The asterisk (*) is a wildcard that means "any characters". So `*.txt` means "any file that ends with .txt". This command moves ALL .txt files to Documents at once.
```bash
mv *.txt ~/Documents/
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Rename a directory
Just like with files, you can rename folders too. This changes "old_folder" to "new_folder" - everything inside stays the same.
```bash
mv old_folder new_folder
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Move a directory
This moves the entire "project" folder from your Desktop to your Documents folder. All the files and subfolders inside "project" come along for the ride.
```bash
mv ~/Desktop/project ~/Documents/
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Interactive mode (prompt before overwriting)
The `-i` flag makes mv ask you "Are you sure?" before overwriting any existing files. This is super helpful to prevent accidentally destroying important files.
```bash
mv -i source.txt destination.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Verbose mode (show what's happening)
The `-v` flag makes mv "chatty" - it tells you exactly what it's doing as it moves each file. Great for seeing what's happening, especially with wildcards.
```bash
mv -v *.pdf ~/Documents/
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Create backup before overwriting
The `-b` flag creates a backup copy before overwriting any existing file. The backup gets a `~` added to the end of its name (like `important.txt~`).
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
When file or folder names have spaces, you need to either wrap them in quotes or use a backslash before each space. Otherwise, the command line thinks each word is a separate file.
```bash
mv "My Document.txt" "Final Document.txt"
# or
mv My\ Document.txt Final\ Document.txt
```
<REPLACE_WITH_IMAGE_OR_GIF>
