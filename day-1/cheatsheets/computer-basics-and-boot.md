# Cheatsheet - Computer basics & boot chain

## Components
| Part | Job | Volatile? | Speed |
|---|---|---|---|
| CPU | runs instructions | n/a (registers: yes) | fastest |
| RAM | working memory | yes | fast |
| SSD/HDD | permanent storage | no | slower |
| Firmware (BIOS/UEFI) | first code at boot | no | n/a |

## Fetch-Decode-Execute
`fetch instruction -> decode it -> execute -> write result -> next`

## Boot order in one line
`Power -> Firmware (POST) -> Boot device -> Bootloader -> Kernel -> Init -> Login`

## BIOS vs UEFI
- BIOS: MBR, 16-bit, legacy.  UEFI: GPT, ESP (FAT32), Secure Boot.

## Handy commands (Linux)
```bash
lscpu                 # CPU info
free -h               # RAM usage
lsblk                 # disks and partitions
sudo fdisk -l         # partition table (MBR/GPT)
[ -d /sys/firmware/efi ] && echo UEFI || echo BIOS   # which boot mode?
dmesg | head -50      # early kernel boot messages
systemd-analyze       # time spent in firmware / loader / kernel / userspace
```

## Handy commands (Windows)
```powershell
msinfo32              # shows BIOS Mode (UEFI/Legacy) and Secure Boot state
Get-Disk              # disk and partition style (MBR/GPT)
```

## Remember
- Programs run from RAM, not the disk.
- Bootkits live below the OS -> Secure Boot + disk encryption help.
