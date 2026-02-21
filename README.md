# Garry ☁  
### Deterministic AirVPN wrapper for eddie-cli`

```
==========================================================

   ██████╗  █████╗ ██████╗ ██████╗ ██╗   ██╗
   ██╔════╝ ██╔══██╗██╔══██╗██╔══██╗╚██╗ ██╔╝
   ██║  ███╗███████║██████╔╝██████╔╝ ╚████╔╝
   ██║   ██║██╔══██║██╔══██╗██╔══██╗  ╚██╔╝
   ╚██████╔╝██║  ██║██║  ██║██║  ██║   ██║
    ╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝   ╚═╝   for ☁ AirVPN

==========================================================
```

If you use AirVPN then you'll undoubtedly know Eddie.

Well I don't like Eddie, so meet Garry.

In fact, Eddie stinks!

---

Garry is a deterministic wrapper around `eddie-cli` designed to:

- Launch AirVPN sessions cleanly  
- Support foreground and background modes  
- Track session PID state  
- Verify egress IPv4 and IPv6  
- Perform IPv4 country identity lookup  
- Provide simple `--status` and `--disconnect` control  

---

## Features

- Quiet background execution (no CLI noise)
- Optional foreground verbose mode
- PID tracking for clean disconnect
- IPv4 + IPv6 external IP detection
- IPv4 geo identity lookup
- Automatic session log overwrite per run
- Daemon-free operation

---

## Usage

### Connect (background mode)

```bash
./garry <server-name>
```

Example:

```bash
./garry Alnitak
```

- Runs `eddie-cli` politely and quietly  
- Intentional wait for tunnel stabilization  
- Logs IPv4, IPv6, and IPv4 country identity  
- Prints the current session report  

---

### Connect (foreground mode)

```bash
./garry <server-name> --foreground
```

- Runs `eddie-cli` attached to your terminal  
- Shows full verbose output  
- Ctrl+C cleanly stops the session  
- No PID tracking in this mode  

---

### Check Status

```bash
./garry --status
```

Reports whether the last background session PID is still active.

---

### Disconnect

```bash
./garry --disconnect
```

Stops the background `eddie-cli` session started by Garry.

---

## Dependencies

Required:

- `eddie-cli`
- `curl`
- `geoiplookup`

## Example Output

```
==========================================================
Garry Egress Check  |  2026-02-21T04:12:03+00:00
Server: Alnitak
Eddie PID: 34821
Wait: 45s

IPv4: PRINT_IPV4_ADDRESS
GeoIP Country Edition: NL, Netherlands

IPv6: PRINT_IPV6_ADDRESS
==========================================================
```

---

## License

MIT License

Copyright (c) 2026 Christopher Jones

Permission is hereby granted, free of charge, to any person obtaining a copy  
of this software and associated documentation files (the "Software"), to deal  
in the Software without restriction, including without limitation the rights  
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell  
copies of the Software, and to permit persons to whom the Software is  
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all  
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR  
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,  
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE  
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER  
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,  
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE  
SOFTWARE.
