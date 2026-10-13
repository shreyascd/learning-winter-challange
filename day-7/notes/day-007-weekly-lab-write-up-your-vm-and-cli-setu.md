# Day 007 - Weekly lab: write up your VM and CLI setup as a README

Phase 1 - Foundation - Computers & Networks | W01 - D7 | Mon 12 Oct 2026

## Week 1 in review
This week covered the foundation of how computers, operating systems and the command line work.

- **Day 1 - Computers and boot chain:** CPU fetch-decode-execute, RAM vs disk, firmware (BIOS/UEFI), POST, bootloader, kernel, init.
- **Day 2 - Operating systems:** kernel vs user space, system calls, processes vs threads, scheduler, Windows (NT), Linux (monolithic) and macOS (XNU) differences.
- **Day 3 - File systems and paths:** NTFS, ext4, APFS, FAT32/exFAT, absolute vs relative paths, case sensitivity, extensions as labels, archive formats and zip slip.
- **Day 4 - Virtualization:** Type 1 vs Type 2 hypervisors, snapshots (not backups), NAT, bridged, host-only and internal networking, safe-lab checklist.
- **Day 5 - Command line:** cmd vs PowerShell vs bash, `/?` and `Get-Help`, object pipelines, recognising encoded PowerShell.
- **Day 6 - Binary, hex and encodings:** bits and bytes, hex, ASCII, UTF-8, base64 (encoding, not encryption), homoglyphs.

## What the weekly README is for
The README is the front page of this repo. It tells anyone (including me later) what my lab machine is, how it is set up, and where the evidence is. It is the first thing a reviewer or recruiter would read, so it must be accurate and specific.

## What a good setup write-up contains
- Host machine: OS, CPU features (virtualization enabled?), RAM, disk.
- Hypervisor: VirtualBox version.
- VMs: names, OS, resources, network adapters and modes.
- CLI setup: shells used (bash, PowerShell, cmd), git version, editor.
- Evidence: screenshots of key steps, command outputs, and the snapshot list.
- Known issues and what I would change next time.

## Questions to revisit
- Which of my setup choices would I change if I rebuilt the lab tomorrow?
- What evidence would convince a reviewer that the lab really works?
