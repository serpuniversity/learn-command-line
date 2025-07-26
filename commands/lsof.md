# `lsof`

> _"What's hogging my port?!"_

The `lsof` command shows you what files and network connections are open on your system. Think of it as your computer's "who's using what" detective - it can tell you exactly which programs are using which files, ports, and network connections.

<a href="#" target="_blank">
<img src="#" width="1000px">
</a>

## Name

`lsof` - list open files (and network connections)

## Mnemonic

`lsof` stands for **l**i**s**t **o**pen **f**iles.

## What Does lsof Actually Show?

In Unix/Linux, **everything is a file** - including network connections! So `lsof` shows you:
- Regular files that programs have open
- Network connections (TCP/UDP sockets) 
- Devices and pipes
- Directories that processes are using

It's like having X-ray vision into what every program on your computer is actually doing.

## Syntax & Common Usage

The basic syntax is simple, but the output can be overwhelming:

```bash
lsof [options] [files/processes]
```

## Output Levels: From Massive to Minimal

Here's how different `lsof` commands compare in terms of output volume:

| Command | What it shows | Amount of output |
|---------|---------------|------------------|
| `lsof` | Everything (all open files/sockets) | 🚨 **Massive** |
| `lsof -i` | Only Internet-related connections | 🌐 **Smaller** |
| `lsof -i -nP` | Internet connections, numeric IPs/ports | 🌐+🧠 **Clear** |
| `lsof -i :3000` | Only processes using port 3000 | 🎯 **Minimal** |
| `lsof -c node` | Only files opened by "node" processes | 🎯 **Focused** |

## Examples

### The nuclear option (show EVERYTHING)
```bash
lsof
```
This shows EVERY open file on your entire system. Prepare for information overload! You'll see thousands of entries. It's like asking "what's everyone in the city doing right now?" - technically useful, but overwhelming.

<REPLACE_WITH_IMAGE_OR_GIF>

### Show only network connections
```bash
lsof -i
```
The `-i` flag filters to only **i**nternet connections (TCP/UDP). This is much more manageable and perfect for seeing what's talking to the network.

<REPLACE_WITH_IMAGE_OR_GIF>

### Show network connections with clear, readable output
```bash
lsof -i -nP
```
This adds two crucial flags:
- `-n` = show **n**umeric IP addresses (no slow DNS lookups)
- `-P` = show **P**ort numbers instead of service names

Instead of seeing `localhost:http-alt`, you'll see `127.0.0.1:8080` - much clearer!

<REPLACE_WITH_IMAGE_OR_GIF>

### Find what's using a specific port
```bash
lsof -i :3000
lsof -i :80
lsof -i :22
```
This is the money shot! When you get "port already in use" errors, this tells you exactly what program is hogging that port. Essential for web developers!

<REPLACE_WITH_IMAGE_OR_GIF>

### Show only what a specific program is doing
```bash
lsof -c node
lsof -c python
lsof -c chrome
```
The `-c` flag shows all files opened by processes whose **c**ommand name matches. Perfect for debugging what a specific application is up to.

<REPLACE_WITH_IMAGE_OR_GIF>

### Show TCP connections only
```bash
lsof -i TCP
```
Sometimes you only care about TCP connections (web servers, SSH, etc.) and want to ignore UDP traffic.

<REPLACE_WITH_IMAGE_OR_GIF>

### Show listening ports only
```bash
lsof -i -sTCP:LISTEN
```
This shows only ports that are **listening** for incoming connections - basically, what servers are running on your machine.

<REPLACE_WITH_IMAGE_OR_GIF>

### Find what's using a port range
```bash
lsof -i :8000-9000
```
Check a whole range of ports at once. Useful for development when you're not sure which port your app grabbed.

<REPLACE_WITH_IMAGE_OR_GIF>

### Show files opened by a specific process ID
```bash
lsof -p 1234
```
If you know a process ID (PID), this shows everything that process has open. Great for debugging resource usage.

<REPLACE_WITH_IMAGE_OR_GIF>

### Monitor network activity in real-time
```bash
lsof -i -r 2
```
The `-r 2` flag refreshes every 2 seconds, giving you a live view of network connections. Like `top` but for network activity!

<REPLACE_WITH_IMAGE_OR_GIF>

### Show connections to a specific host
```bash
lsof -i @google.com
lsof -i @192.168.1.1
```
See all connections to a specific server or IP address. Useful for monitoring what's talking to external services.

<REPLACE_WITH_IMAGE_OR_GIF>

## Understanding the Output

When you run `lsof -i -nP`, you'll see columns like this:

```
COMMAND   PID USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
node      123 john   23u  IPv4  12345      0t0  TCP 127.0.0.1:3000 (LISTEN)
chrome    456 john   45u  IPv4  67890      0t0  TCP 192.168.1.100:54321->142.250.191.14:443 (ESTABLISHED)
```

**Key columns explained:**
- **COMMAND**: What program is this?
- **PID**: Process ID number
- **USER**: Who's running it?
- **FD**: File descriptor (ignore this for now)
- **NAME**: The actual connection info!

**Connection states:**
- **(LISTEN)**: Waiting for incoming connections (server)
- **(ESTABLISHED)**: Active connection in progress
- **->**: Shows direction (your machine -> remote server)

## Command Quick Reference

| Command | What It Shows | Use Case |
|---------|---------------|----------|
| `lsof` | Everything | Nuclear option - information overload |
| `lsof -i` | All network connections | See what's talking to the network |
| `lsof -i -nP` | Network connections (clear format) | Best general network overview |
| `lsof -i :PORT` | What's using specific port | "Port in use" errors |
| `lsof -c PROGRAM` | Files opened by program | Debug specific application |
| `lsof -i TCP` | TCP connections only | Focus on TCP traffic |
| `lsof -i -sTCP:LISTEN` | Listening ports only | See what servers are running |
| `lsof -p PID` | Files opened by process ID | Debug specific process |
| `lsof -i -r 2` | Real-time network monitoring | Live network activity |
| `lsof -i @host` | Connections to specific host | Monitor external connections |

## Tips for Beginners

### Start small, then go nuclear
```bash
# Start here (focused):
lsof -i :3000

# Then expand (network overview):
lsof -i -nP

# Nuclear option last (everything):
lsof
```

### Common "port in use" debugging
```bash
# Error: "Port 3000 already in use"
lsof -i :3000
# Find the PID, then kill it:
kill 1234
```

### Use grep to filter the chaos
```bash
lsof -i -nP | grep :80        # Only port 80
lsof -i -nP | grep LISTEN     # Only listening ports
lsof -i -nP | grep node       # Only node processes
```

### Why use -nP together?
- **Without**: `localhost:http-alt (LISTEN)` 🤔 What port is that?
- **With -nP**: `127.0.0.1:8080 (LISTEN)` 😎 Ah, port 8080!

### Real-world scenarios
- **Web dev**: `lsof -i :3000` → "What killed my React server?"
- **DevOps**: `lsof -i -sTCP:LISTEN` → "What services are exposed?"
- **Debugging**: `lsof -c mysql` → "What files is MySQL touching?"
- **Security**: `lsof -i -nP | grep ESTABLISHED` → "What's my computer talking to?"

### Permission note
Some `lsof` commands need `sudo` to see all processes:
```bash
sudo lsof -i -nP    # See everything, including other users' processes
```

Remember: `lsof` is your detective tool for the question "what's my computer actually doing?" When something's broken, `lsof` usually has the answer!
