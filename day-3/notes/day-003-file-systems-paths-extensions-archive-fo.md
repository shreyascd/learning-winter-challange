# Day 003 - File systems, paths, extensions, archive formats

Phase 1 - Foundation - Computers & Networks | W01 - D3

## File systems
A file system is how an OS organises data on a storage device. It stores names, sizes, timestamps, permissions and the locations of each file's data blocks.
- **NTFS** - Windows default. Supports permissions, journaling, encryption (EFS).
- **ext4** - common Linux default. Journaling, permissions (rwx, owner/group).
- **APFS** - macOS default. Snapshots, encryption, copy-on-write.
- **FAT32 / exFAT** - simple, widely compatible (USB drives, SD cards). FAT32 has a 4 GB file size limit.

Journaling records changes before writing them, so the file system can recover after a crash.

## Paths
- **Absolute path** - starts from the root: `/home/shreyas/notes.txt` (Linux) or `C:\Users\Shreyas\notes.txt` (Windows).
- **Relative path** - starts from the current directory: `notes/day-003.md`.
- `.` means the current directory, `..` means the parent directory.
- Linux paths are **case-sensitive** (`File.txt` and `file.txt` are different). Windows and default macOS are case-insensitive.
- Path separators: `/` on Linux/macOS, `\` on Windows.

## File extensions
An extension (`.pdf`, `.exe`) is a hint for the OS and apps about what the file is. It is not proof. Anyone can rename a file.
- Attackers use **double extensions** (`invoice.pdf.exe`) and hidden extensions (Windows hides known extensions by default).
- Check what a file really is by its **magic bytes** (the first bytes of the content), for example with the `file` command.

## Archive formats
- **zip** - archive and compression together. Common on Windows and everywhere else.
- **tar** - archive only (bundles files, no compression). Common on Linux.
- **tar.gz / .tgz** - tar archive compressed with gzip.
- **7z, rar** - high compression; rar needs a proprietary tool to create.

Security points about archives:
- **Zip slip / path traversal** - an entry named `../../etc/cron.d/x` can write outside the folder you extract to. Good tools strip or block these.
- **Zip bombs** - tiny files that expand to huge sizes and fill the disk.
- Always list contents first (`tar -tzf`, `unzip -l`) before extracting untrusted archives.

## Permissions (Linux)
`ls -l` shows `-rw-r--r--`: type, then owner, group and others, each with read (r), write (w) and execute (x). `chmod` changes them.

## Integrity
A hash (SHA-256) is a fingerprint of a file. If the hash changes, the file changed. Analysts compare hashes to check downloads and evidence.

## Questions to revisit
- How does journaling in ext4 differ from copy-on-write in APFS?
- Why does Linux need the execute bit on directories?
