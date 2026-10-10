# Day 005 - Command line tour: cmd and PowerShell basics, help flags

Phase 1 - Foundation - Computers & Networks | W01 - D5 | Sat 10 Oct 2026

## Why the command line
GUIs hide what is happening. The command line shows the exact action, can be repeated and scripted, and is how analysts and admins work on servers and during incident response.

## cmd vs PowerShell vs bash
- **cmd** - the old Windows shell. Text in, text out. Simple commands like `dir`, `cd`, `copy`, `type`.
- **PowerShell** - the modern Windows shell. Uses **verb-noun** cmdlets (`Get-ChildItem`, `Get-Process`). Pipelines pass **objects** (with properties), not just text.
- **bash** - the common Linux/macOS shell. Text-based pipelines (`ps aux | grep ssh`).

## Common equivalents
| Task | cmd | PowerShell | bash |
|---|---|---|---|
| List files | `dir` | `Get-ChildItem` (or `ls`, `dir`) | `ls -la` |
| Show a file | `type file.txt` | `Get-Content file.txt` (or `cat`) | `cat file.txt` |
| Processes | `tasklist` | `Get-Process` | `ps aux` |
| Current folder | `cd` | `Get-Location` (or `pwd`) | `pwd` |

PowerShell aliases (`ls`, `cat`, `dir`, `ps`) map to the real cmdlets. Knowing the full name helps when reading scripts.

## Help flags and built-in help
- **cmd:** `dir /?`, `netstat /?`. Most built-in commands accept `/?`.
- **PowerShell:** `Get-Help Get-Process`, `Get-Help Get-ChildItem -Examples`, `Get-Help Get-Process -Full`.
- **Find a command:** `Get-Command *process*` (PowerShell) or `where` / `help` (cmd).
- **Object members:** `Get-Process | Get-Member` shows the properties you can filter on.
- **Linux equivalents:** `man ls`, `ls --help`, `apropos` to search manuals.
- **Executables:** most `.exe` tools accept `/?` or `-h`/`--help`. Try both.

## Security points
- PowerShell is a big attack surface. Attackers use `powershell -enc` (encoded commands) and download-and-run one-liners. Logging of script blocks helps detect them.
- Read a command before pasting it from the internet. Many "fix" commands are malicious.
- Run admin shells only when needed. Check whether you are elevated with `whoami /groups` (cmd).

## Questions to revisit
- What is the difference between `Get-Process` and `tasklist` in what they return?
- How do I see what a PowerShell pipeline is passing along with `Get-Member`?
