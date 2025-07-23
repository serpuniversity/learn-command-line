# `mkdir`

> _"Make new directory"_

The `mkdir` command makes directories (folders). It's like creating a new folder in your file manager, but from the command line. You can make one folder or a whole bunch at once.

<a href="#" target="_blank">
<img src="#" width="1000px">
</a>

## Name

`mkdir` - make directories

## Mnemonic

`mkdir` stands for **m**a**k**e **dir**ectory.

## Syntax & Common Usage

You'll typically use the `mkdir` command with directory names and paths similar to how you navigate your filesystem.

For example:
```bash
mkdir [options] [directory_name]
```

## Examples

### Create a single directory
The most basic use - just make one new folder in your current location.
```bash
mkdir my_folder
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Create multiple directories at once
Instead of running mkdir three times, you can create several folders in one command by listing them with spaces.
```bash
mkdir folder1 folder2 folder3
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Create a directory with a full path
Create a folder somewhere else on your system by specifying the complete path to where you want it.
```bash
mkdir ~/Documents/new_project
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Create nested directories with -p
This is the magic option! The `-p` flag creates "parent" directories - meaning if you want to create `folder1/folder2/folder3` but `folder1` and `folder2` don't exist yet, it'll create them all for you.
```bash
mkdir -p projects/web/frontend
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Create complex nested structures
You can create entire directory trees in one command. This creates the `app` folder, then `src` and `assets` inside it, then `css` and `js` inside `src`.
```bash
mkdir -p app/src/{css,js} app/assets
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Create nested directories from home
Combine the `-p` option with paths from your home directory to build folder structures anywhere.
```bash
mkdir -p ~/Documents/projects/website/images
```
<REPLACE_WITH_IMAGE_OR_GIF>

### What happens without -p?
If you try to create nested directories without `-p`, mkdir will complain that the parent directories don't exist. That's when you know you need the `-p` flag!
```bash
mkdir folder1/folder2/folder3
# This fails! Use mkdir -p instead
```
<REPLACE_WITH_IMAGE_OR_GIF>

## Command Quick Reference

| Command | What It Does | Example |
|---------|--------------|---------|
| `mkdir folder` | Create single directory | `mkdir documents` |
| `mkdir folder1 folder2` | Create multiple directories | `mkdir photos videos music` |
| `mkdir ~/path/folder` | Create directory at specific path | `mkdir ~/Desktop/new_project` |
| `mkdir -p path/to/folder` | Create nested directories | `mkdir -p projects/app/src` |
| `mkdir -p {dir1,dir2}/sub` | Create multiple nested structures | `mkdir -p {web,mobile}/assets` |

## Tips

### When to Use -p
Use `-p` whenever you want to create a folder inside another folder that might not exist yet. It's like saying "create this path, and if any parent folders are missing, create those too."

### Understanding the Error Without -p
```bash
mkdir folder1/folder2
# Error: mkdir: folder1: No such file or directory
```
This error means `folder1` doesn't exist, so mkdir can't create `folder2` inside it. Add `-p` to fix this!

### Creating Directory Trees
The curly brace syntax `{dir1,dir2}` is super handy for creating multiple similar structures:
```bash
mkdir -p project/{frontend,backend}/{src,tests}
```
This creates:
- project/frontend/src
- project/frontend/tests  
- project/backend/src
- project/backend/tests

### Handling Spaces in Directory Names
If your directory name has spaces, wrap it in quotes:
```bash
mkdir "My New Project"
mkdir -p "Documents/My Projects/Website Files"
```
