# Lab - Day 005: 20 commands I actually ran today

Rule: only list commands I really ran. Paste the real output (or a short excerpt) under each one.

## Help and discovery
1. `dir /?`
   - output: (paste)
2. `where ping`
   - output: (paste)
3. `Get-Help Get-Process -Examples`
   - output: (paste)
4. `Get-Command *service*`
   - output: (paste)
5. `Get-Process | Get-Member | Select-Object -First 10`
   - output: (paste)

## Files and folders
6. `cd`
   - output: (paste)
7. `dir`
   - output: (paste)
8. `Get-ChildItem -Force`
   - output: (paste)
9. `type notes.txt` (or `Get-Content`)
   - output: (paste)
10. `mkdir day-5-test`
    - output: (paste)

## System and network
11. `whoami`
    - output: (paste)
12. `whoami /groups`
    - output: (paste)
13. `tasklist`
    - output: (paste)
14. `ipconfig /all`
    - output: (paste)
15. `systeminfo | findstr /B /C:"OS Name" /C:"System Type"`
    - output: (paste)

## Pipelines and filtering
16. `Get-Process | Sort-Object CPU -Descending | Select-Object -First 5`
    - output: (paste)
17. `Get-Service | Where-Object Status -eq Running | Measure-Object`
    - output: (paste)

## Safe reading
18. `Get-FileHash .\notes.txt -Algorithm SHA256`
    - output: (paste)
19. `Get-Item .\notes.txt | Select-Object FullName, Length`
    - output: (paste)
20. `netstat /?`
    - output: (paste)

## Notes
- Which command was the most useful and why?
- Which command did I need `/?` or `Get-Help` for?
