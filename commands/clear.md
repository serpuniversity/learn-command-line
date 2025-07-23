# `clear`

> _"How do I clean up this window?"_

The `clear` command wipes your terminal screen clean. It's like hitting the refresh button - all that messy text from previous commands disappears, giving you a fresh, clean slate to work with.

<a href="#" target="_blank">
<img src="#" width="1000px">
</a>

## Name

`clear` - clear the terminal screen

## Mnemonic

`clear` stands for **clear** (it's pretty literal!).

## Syntax & Common Usage

The `clear` command is super simple - you just type it and your screen gets cleaned up.

For example:
```bash
clear
```

## Examples

### Clear the terminal screen
The most basic use - just wipe away all the clutter and start fresh. Perfect when your terminal is full of old commands and output.
```bash
clear
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Quick keyboard shortcut
Instead of typing `clear` every time, just press Ctrl+L. It's way faster and does the same thing (mostly).
```bash
# Just press: Ctrl+L
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Clear when you're lost in output
After running commands that produce lots of text (like `ls -la` in a big directory), use clear to get your bearings back.
```bash
ls -la /usr/bin
clear  # Ahh, much better!
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Clear before important commands
Good practice to clear the screen before running important or dangerous commands so you can see the output clearly.
```bash
clear
sudo rm -rf /old_backup  # Now you can clearly see what happens
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Clear in scripts
Use clear in shell scripts to give users a clean interface when your script starts.
```bash
#!/bin/bash
clear
echo "Welcome to my awesome script!"
```
<REPLACE_WITH_IMAGE_OR_GIF>

### Clear but keep history (Ctrl+L behavior)
The `clear -x` option clears the visible screen but keeps your scroll-back history - same as pressing Ctrl+L.
```bash
clear -x
```
<REPLACE_WITH_IMAGE_OR_GIF>

### When clear isn't enough - use reset
If your terminal gets really messed up (garbled text, weird characters), `reset` does a deeper clean than `clear`.
```bash
reset  # Nuclear option - resets everything
```
<REPLACE_WITH_IMAGE_OR_GIF>

## Command Quick Reference

| Command | What It Does | When to Use |
|---------|--------------|-------------|
| `clear` | Clear terminal screen | When screen is cluttered |
| `Ctrl+L` | Quick clear (keyboard shortcut) | Most common way to clear |
| `clear -x` | Clear but keep scroll history | When you might need to scroll back |
| `reset` | Deep clean + reset terminal | When terminal is acting weird |
| `Ctrl+Shift+K` | Clear everything (some terminals) | Alternative to clear in some terminals |

## Tips

### Keyboard Shortcuts are Faster
- **Ctrl+L**: This is what you'll actually use 99% of the time. Much faster than typing `clear`
- **Ctrl+Shift+K**: Works in some terminals (like GNOME Terminal) to completely clear including history

### clear vs Ctrl+L - What's the Difference?
- `clear`: Completely clears the screen and scroll-back buffer
- `Ctrl+L`: Clears the visible screen but you can still scroll up to see old output
- In practice, both work great for cleaning up your workspace

### When Your Terminal Gets Weird
Sometimes programs crash and leave your terminal in a weird state (strange characters, wrong colors, etc.). That's when you need:
```bash
reset  # Fixes most terminal weirdness
```

### Creating Aliases
You can make your own shortcuts:
```bash
alias c='clear'  # Now just type 'c' to clear
alias cls='clear'  # For Windows refugees
```

### Why Clear Your Terminal?
- **Focus**: Removes distracting old output
- **Fresh start**: Clean slate for new work
- **Screenshots**: Clean terminal looks more professional
- **Debugging**: Easier to see new output when screen isn't cluttered
