# `cd`

> _"How do I get out of here?"_

The `cd` command changes the current working directory (folder), allowing you to move between directories (folders) on the filesystem.

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
<img width="1728" height="1078" alt="image" src="https://github.com/user-attachments/assets/93cbcb02-f538-4557-a5f9-403637dd4150" />

### Move up two directories
```bash
cd ../..
```
<img width="1728" height="1080" alt="image" src="https://github.com/user-attachments/assets/8ce87648-0790-4ec7-996d-393867c902bc" />

### Move to parent folder's sibling directory
```bash
cd ../another-directory
```
<img width="1726" height="1077" alt="image" src="https://github.com/user-attachments/assets/69ff8527-e9c0-4b16-a477-f4982c1229c3" />

### Switch back to previously directory
```bash
cd -
```
<img width="1728" height="1080" alt="image" src="https://github.com/user-attachments/assets/5ac14303-1f75-41b6-a87e-02098ad0a6f8" />

### Move the user's home directory
```bash
cd
cd ~
cd /Users/<username>
cd $HOME
```
<img width="1728" height="1081" alt="image" src="https://github.com/user-attachments/assets/aaddeac7-58fe-4c36-80a7-f76f4e1b6adb" />

### Move directly to the filesystem's root directory
```bash
cd /
```
<img width="1728" height="1081" alt="image" src="https://github.com/user-attachments/assets/ebb8913f-19e0-4b8a-a0c3-f96a5d140125" />


### Move to a specific directory
```bash
cd ~/Desktop
cd [directoryName]
cd [directoryName/subDirectoryName]
```
<img width="1728" height="1084" alt="image" src="https://github.com/user-attachments/assets/d1c3ffb7-0c3d-47a9-a340-303766a85405" />

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
<img width="1727" height="1080" alt="image" src="https://github.com/user-attachments/assets/b29472ec-e89e-4c6a-8468-7f06642c2393" />



