# `curl`

> _"I need to grab that file from the internet!"_

The `curl` command downloads files from the internet or talks to websites and APIs. It's like your command-line web browser - you give it a web address and it fetches whatever is there.

<a href="#" target="_blank">
<img src="#" width="1000px">
</a>

## Name

`curl` - transfer data from or to a server

## Mnemonic

`curl` stands for **C**lient **URL** (though some say it stands for **c**url **URL**).

## Syntax & Common Usage

You'll typically use curl to download files or check websites:

```bash
curl [options] [URL]
```

## Examples

### Just look at a website (display content)
```bash
curl https://example.com
```
This downloads the webpage and shows it right in your terminal. It's like "view source" in your browser, but in the command line!

<REPLACE_WITH_IMAGE_OR_GIF>

### Download a file and save it with a new name
```bash
curl -o myfile.pdf https://example.com/document.pdf
```
The `-o` flag lets you save the downloaded file with whatever name you want. Super handy when the original filename is messy or long.

<REPLACE_WITH_IMAGE_OR_GIF>

### Download a file and keep its original name
```bash
curl -O https://example.com/document.pdf
```
The `-O` (capital O) flag saves the file with the same name it has on the website. Easy way to grab files without thinking of new names!

<REPLACE_WITH_IMAGE_OR_GIF>

### Follow redirects (when websites move stuff)
```bash
curl -L https://example.com/oldpage
```
Sometimes websites redirect you to new URLs. The `-L` flag makes curl follow those redirects automatically instead of just showing you an error message.

<REPLACE_WITH_IMAGE_OR_GIF>

### Download with a progress bar
```bash
curl -# -O https://example.com/bigfile.zip
```
The `-#` flag shows a nice progress bar instead of the confusing default progress meter. Perfect for big downloads so you know how much is left!

<REPLACE_WITH_IMAGE_OR_GIF>

### Silent download (no output)
```bash
curl -s -O https://example.com/file.txt
```
The `-s` flag makes curl "silent" - it won't show any progress or error messages. Great for scripts where you don't want clutter in the output.

<REPLACE_WITH_IMAGE_OR_GIF>

### Resume a broken download
```bash
curl -C - -O https://example.com/hugefile.zip
```
If your download got interrupted, `-C -` tells curl to continue from where it left off. Super useful for big files on slow connections!

<REPLACE_WITH_IMAGE_OR_GIF>

### Check if a website is working (headers only)
```bash
curl -I https://example.com
```
The `-I` flag only fetches the "headers" (like checking if someone's home without going inside). Great for testing if a website is up and running.

<REPLACE_WITH_IMAGE_OR_GIF>

### Download multiple files at once
```bash
curl -O https://example.com/file1.pdf -O https://example.com/file2.txt
```
You can download several files in one command by using `-O` before each URL. Much faster than running curl multiple times!

<REPLACE_WITH_IMAGE_OR_GIF>

### Limit download speed (be nice to servers)
```bash
curl --limit-rate 100k -O https://example.com/file.zip
```
The `--limit-rate` option lets you slow down your download so you don't overwhelm the server. Use `k` for kilobytes, `m` for megabytes.

<REPLACE_WITH_IMAGE_OR_GIF>

### See what's happening (verbose mode)
```bash
curl -v https://example.com
```
The `-v` flag shows you EVERYTHING that's happening - like watching curl have a conversation with the website. Great for debugging when things go wrong.

<REPLACE_WITH_IMAGE_OR_GIF>

### Pretend to be a different browser
```bash
curl -A "Mozilla/5.0 (Windows NT 10.0; Win64; x64)" https://example.com
```
Some websites block curl or show different content to different browsers. The `-A` flag lets you pretend to be Chrome, Firefox, etc.

<REPLACE_WITH_IMAGE_OR_GIF>

## Command Quick Reference

| Command | What It Does | Example |
|---------|--------------|---------|
| `curl URL` | View content in terminal | `curl https://example.com` |
| `curl -o name URL` | Save with custom name | `curl -o file.pdf https://site.com/doc.pdf` |
| `curl -O URL` | Save with original name | `curl -O https://site.com/file.zip` |
| `curl -L URL` | Follow redirects | `curl -L https://short.url/abc123` |
| `curl -I URL` | Get headers only | `curl -I https://example.com` |
| `curl -# URL` | Show progress bar | `curl -# -O https://site.com/big.zip` |
| `curl -s URL` | Silent mode | `curl -s -O https://site.com/file.txt` |
| `curl -C - URL` | Resume download | `curl -C - -O https://site.com/huge.zip` |
| `curl -v URL` | Verbose (debug) mode | `curl -v https://example.com` |
| `curl --limit-rate 100k URL` | Limit speed | `curl --limit-rate 500k -O file.zip` |

## Tips

### Common mistake: No output file specified
```bash
# This will dump the file content to your screen (messy!)
curl https://example.com/document.pdf

# Do this instead:
curl -O https://example.com/document.pdf
```

### When downloads fail
If curl says "moved" or shows an error, try adding `-L` to follow redirects - this fixes most issues!

### File will be saved in current directory
Whatever folder you're in when you run curl is where the file gets saved. Use `pwd` to check where you are first.

### Curl vs wget
- `curl` = more powerful, better for APIs and complex stuff
- `wget` = simpler for basic file downloads
- Both are great, curl is more widely available
