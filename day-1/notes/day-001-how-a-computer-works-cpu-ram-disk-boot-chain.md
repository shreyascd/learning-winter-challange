# Day 001 - How a computer works: CPU, RAM, disk, boot chain (BIOS/UEFI to OS)

Phase 1 - Foundation - Computers & Networks | W01 - D1 | Tue 06 Oct 2026

## The big picture
A computer takes instructions and data, processes them, and stores or shows the result.
Four parts do most of the work:

- **CPU** - executes instructions. It fetches an instruction, decodes it, executes it, repeats (fetch-decode-execute cycle). Has a few registers (tiny, fastest storage) and caches (L1/L2/L3).
- **RAM** - fast, temporary working memory. Holds the running programs and their data. Loses everything when power is off (volatile).
- **Disk (SSD/HDD)** - slow, permanent storage. Keeps files, the OS and programs when the power is off (non-volatile).
- **Motherboard / buses** - the wiring that lets all of the above talk to each other.

## Speed hierarchy (fast/small to slow/big)
Registers -> CPU cache -> RAM -> SSD -> HDD -> network storage.
Programs are loaded disk -> RAM, because the CPU can't work directly from the disk fast enough.

## The boot chain
1. **Power on** - the power supply stabilises, the CPU resets and jumps to a fixed address in firmware.
2. **Firmware (BIOS or UEFI)** - stored on a chip on the motherboard. Runs POST (power-on self test) to check CPU, RAM, keyboard, etc.
3. **Find a boot device** - firmware checks the boot order (SSD, USB, network).
   - *BIOS (legacy)* reads the MBR (first 512 bytes of disk) and runs the tiny code inside it.
   - *UEFI (modern)* reads an EFI System Partition (FAT32) and loads a `.efi` bootloader file directly. Supports GPT disks, large drives and Secure Boot.
4. **Bootloader** (GRUB, Windows Boot Manager) - loads the OS kernel into RAM, lets you pick between OSes.
5. **Kernel** - initialises drivers, mounts the root filesystem, sets up memory management and processes.
6. **Init / service manager** (systemd on Linux, services on Windows) - starts background services.
7. **Login screen / shell** - user space is ready.

## Why this matters for security
- Whoever controls the boot chain controls everything above it. Malware that hides here (bootkits, rootkits) survives OS reinstalls and hides from the OS.
- **Secure Boot** checks that each stage is digitally signed before running it.
- Physical access + boot from USB can bypass OS login, so BIOS passwords and disk encryption matter.

## BIOS vs UEFI quick compare
| | BIOS | UEFI |
|---|---|---|
| Disk layout | MBR (max 2 TB) | GPT (huge disks) |
| Boot code | 512-byte MBR | .efi files on ESP |
| Security | none built-in | Secure Boot |
| Interface | text, keyboard | graphical, mouse |

## Things I want to understand better
- What exactly does the CPU do in the first few microseconds after reset?
- How does Secure Boot's chain of keys work (PK, KEK, db)?
