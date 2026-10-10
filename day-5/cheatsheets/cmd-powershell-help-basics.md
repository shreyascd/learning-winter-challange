# Cheatsheet - cmd and PowerShell basics, help flags

## Getting help
```powershell
Get-Help Get-Process                  # basic help
Get-Help Get-ChildItem -Examples      # usage examples
Get-Help Get-Process -Full            # everything
Get-Command *service*                 # find commands by name
Get-Process | Get-Member              # properties you can use in pipelines
```
```cmd
dir /?
netstat /?
where ping
```
```bash
man ls
ls --help
apropos "network"
```

## Core commands
| Task | cmd | PowerShell | bash |
|---|---|---|---|
| List files | `dir` | `Get-ChildItem` | `ls -la` |
| Read a file | `type notes.txt` | `Get-Content notes.txt` | `cat notes.txt` |
| Copy | `copy a.txt b.txt` | `Copy-Item a.txt b.txt` | `cp a.txt b.txt` |
| Delete | `del file.txt` | `Remove-Item file.txt` | `rm file.txt` |
| Processes | `tasklist` | `Get-Process` | `ps aux` |
| Network | `ipconfig /all` | `Get-NetIPAddress` | `ip addr` |
| Who am I | `whoami` | `whoami /groups` | `id` |

## Pipelines
```powershell
Get-Process | Where-Object CPU -gt 50 | Sort-Object CPU -Descending | Select-Object -First 5
```
```bash
ps aux | sort -nrk 3 | head -5
```

## Security one-liners to recognise (do not run on untrusted machines)
- `powershell -enc <base64>` - encoded command; decode to read it.
- `IEX (New-Object Net.WebClient).DownloadString(...)` - download and run.

## Remember
- PowerShell pipelines pass objects; bash passes text.
- Use `/?` (cmd) or `Get-Help` (PowerShell) before guessing flags.
