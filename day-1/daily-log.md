# Daily log

## Day 001 - Tue 06 Oct 2026
**Topic:** How a computer works - CPU, RAM, disk, boot chain (BIOS/UEFI to OS)

### 3 things learned
1. Programs run from RAM; the disk is only permanent storage that gets loaded into RAM.
2. The boot chain is a relay: firmware -> bootloader -> kernel -> init, and each stage trusts the one before it.
3. UEFI + Secure Boot protects the boot chain from bootkits, which BIOS/MBR never could.

### 1 thing to revisit tomorrow
- How Secure Boot's key hierarchy (PK, KEK, db) actually verifies signatures.
