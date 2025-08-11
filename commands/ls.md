---
title: How to use the `ls` terminal command
tags:
  - command line
  - ls
---

# `ls`

> _"List shit"_

The `ls` command lists things. It shows you what files and folders are in a directory. 

Think of this command as what you unintentionally do every time you open up a folder on your computer by double clicking it. When you do that, you just immediately see all the stuff that's in it. However, on the command line, there's no graphical user interface. So the first thing that you might typically do is type this command to show you what's in it. It's kind of like opening your eyes to see what is located at the place where you currently are.

And since you're not asking to see anything in particular, it's kind of like saying, "Oh, just go ahead and list all the shit that's here."

<a href="#" target="_blank">
<img src="#" width="1000px">
</a>

## Name

`ls` - list directory contents

## Mnemonic

`ls` stands for "list shit"

## Syntax & Common Usage

You'll typically use the `ls` command with the same syntax you're used to for navigating between directories in your filesystem (ie: `..` or `../..` etc.)

For example:
```bash
ls [options] [directory]
```

## Examples

### List files in current directory
Just see what's in the folder you're currently in - the basic, no-frills version.
```bash
ls
```
<REPLACE_WITH_IMAGE_OR_GIF>

### List files with detailed information
The `-l` flag gives you the "long format" - shows permissions, file sizes, dates, and who owns what. Super useful for getting the full picture.
```bash
ls -l
```
<REPLACE_WITH_IMAGE_OR_GIF>

### List all files including hidden ones
The `-a` flag shows "all" files, including the sneaky hidden ones that start with a dot (like `.bashrc` or `.git`). These are usually important system files.
```bash
ls -a
```
<REPLACE_WITH_IMAGE_OR_GIF>

### List all files with detailed information
This combines `-l` and `-a` to give you everything - all files (including hidden ones) with all the details. This is probably the most useful combo.
```bash
ls -la
```
<REPLACE_WITH_IMAGE_OR_GIF>

### List files in a specific directory
Instead of listing your current directory, you can peek into any other directory by specifying its path.
```bash
ls ~/Documents
```
<REPLACE_WITH_IMAGE_OR_GIF>

### List specific directory with details
Combine directory targeting with the long format to get detailed info about files in any folder.
```bash
ls -l ~/Documents
```
<REPLACE_WITH_IMAGE_OR_GIF>

### List specific directory with all files and details
The ultimate combo - see everything in any directory with full details.
```bash
ls -la ~/Documents
```
<REPLACE_WITH_IMAGE_OR_GIF>

## Command Quick Reference

| Command | What It Does | Example |
|---------|--------------|---------|
| `ls` | List files in current directory | `ls` → shows files and folders |
| `ls -l` | Long format with details | `ls -l` → shows permissions, sizes, dates |
| `ls -a` | Show all files (including hidden) | `ls -a` → shows `.bashrc`, `.git`, etc. |
| `ls -la` | All files with details | `ls -la` → everything with full info |
| `ls directory` | List files in specific directory | `ls ~/Documents` → shows Documents folder |
| `ls -l directory` | Long format for specific directory | `ls -l ~/Documents` → Documents with details |
| `ls -la directory` | All files with details in directory | `ls -la ~/Documents` → everything in Documents |

## Tips

### Understanding the Long Format (-l)
When you use `ls -l`, you get columns of info:
- **Permissions**: Who can read/write/execute the file
- **Links**: How many hard links (usually just 1)
- **Owner**: Who owns the file
- **Group**: What group the file belongs to
- **Size**: How big the file is (in bytes)
- **Date/Time**: When it was last modified
- **Name**: The actual filename

### What are Hidden Files?
Files that start with a dot (.) are "hidden" - they don't show up in normal listings. They're usually:
- Configuration files (like `.bashrc`)
- System files (like `.DS_Store` on Mac)
- Application settings (like `.git` folders)

### Combining Options
You can mix and match options: `ls -la`, `ls -al`, `ls -l -a` all do the same thing!
