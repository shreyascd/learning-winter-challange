# Cheatsheet - File systems, paths, extensions, archives

## Navigate (Linux/macOS)
```bash
pwd                      # where am I (absolute path)
ls -la                   # list all files with permissions and hidden files
cd ~/study-repo          # go to a folder (~ = home)
cd ..                    # go up one level
realpath notes.txt       # full absolute path of a file
basename /a/b/c.txt      # c.txt
dirname /a/b/c.txt       # /a/b
```

## Create folders and files
```bash
mkdir -p study-repo/day-3/{notes,cheatsheets,flashcards,labs}   # nested folders in one go
touch day-3/notes/.gitkeep                                       # empty file (keeps folder in git)
tree -L 2 study-repo                                             # view structure (install tree if missing)
```

## Identify a file's real type
```bash
file suspicious.pdf      # reads magic bytes, not the extension
stat notes.txt           # size, times, permissions, inode
sha256sum file.bin       # fingerprint for integrity
```

## Archives
```bash
tar -czvf day-3.tar.gz day-3/    # create tar.gz
tar -tzf day-3.tar.gz            # LIST contents first (safe check)
tar -xzvf day-3.tar.gz -C /tmp/  # extract into /tmp
zip -r day-3.zip day-3/          # create zip
unzip -l day-3.zip               # list zip contents
7z x archive.7z                  # extract 7z (p7zip package)
```

## Windows (PowerShell)
```powershell
Get-ChildItem -Force                       # list incl. hidden
Compress-Archive -Path day-3 -DestinationPath day-3.zip
Expand-Archive -Path day-3.zip -DestinationPath C:\Temp\day3
Get-FileHash .\file.exe -Algorithm SHA256
Get-Item .\file.txt | Select-Object FullName, Length, Attributes
```

## Remember
- Extension is a label, not proof - check magic bytes.
- Linux paths are case-sensitive.
- Always list an archive before extracting it.
