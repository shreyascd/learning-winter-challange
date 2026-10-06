# Lab - Day 001: Draw the boot sequence from memory

## 1. Boot sequence diagram (from memory)
```
 [Power ON]
     |
     v
 [CPU reset -> jumps to firmware address]
     |
     v
 [BIOS / UEFI firmware]  -- POST (check CPU, RAM, devices)
     |
     v
 [Pick boot device by boot order]
     |
     +--> BIOS: read MBR (512 bytes) -> run stage-1 loader
     |
     +--> UEFI: read EFI System Partition -> run .efi loader (Secure Boot check)
     |
     v
 [Bootloader: GRUB / Windows Boot Manager]
     |
     v
 [Kernel loaded into RAM, drivers + root filesystem]
     |
     v
 [Init / systemd -> services]
     |
     v
 [Login screen / shell]
```

## 2. Commands to run on my own machine (paste real output below)
```bash
lscpu | head -20
free -h
lsblk
[ -d /sys/firmware/efi ] && echo "UEFI" || echo "BIOS"
systemd-analyze
```

### My output
```
(paste output here)
```

## 3. Screenshots
- [ ] msinfo32 / BIOS Mode screenshot
- [ ] My hand-drawn diagram photo

## 4. Observations
- Is my machine UEFI or legacy BIOS?
- How long does firmware vs kernel vs userspace take to boot?
