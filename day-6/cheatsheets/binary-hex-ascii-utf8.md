# Cheatsheet - Binary, hex, ASCII, UTF-8

## Key values
| Char | Decimal | Hex | Binary |
|---|---|---|---|
| 0 (digit) | 48 | 0x30 | 00110000 |
| A | 65 | 0x41 | 01000001 |
| a | 97 | 0x61 | 01100001 |
| space | 32 | 0x20 | 00100000 |
| newline | 10 | 0x0A | 00001010 |
| € | 8364 (U+20AC) | - | UTF-8: E2 82 AC |

## Quick conversions
- Binary to decimal: sum the powers of 2 where bits are 1.
- Decimal to hex: divide by 16, read remainders bottom to top.
- Hex digit = 4 bits. `0x4F` = `0100 1111`.

## Verify with Python
```bash
python3 -c "print(ord('H'), hex(ord('H')), bin(ord('H')))"
python3 -c "print(chr(0x6C))"
python3 -c "print(int('01010111', 2))"
python3 -c "print('€'.encode('utf-8').hex(' '))"
python3 -c "print(b'\xe2\x82\xac'.decode('utf-8'))"
```

## Hex and bytes on Linux
```bash
echo -n "A" | xxd            # hex dump of 'A'
echo -n "€" | xxd            # shows the 3 UTF-8 bytes
printf '%x\n' 65             # decimal to hex -> 41
printf '%d\n' 0x41           # hex to decimal -> 65
echo -n "hello" | base64     # encode (not encryption!)
echo "aGVsbG8=" | base64 -d  # decode
```

## PowerShell
```powershell
[Convert]::ToString(72, 2)                       # decimal -> binary: 1001000
[Convert]::ToInt32('48', 16)                      # hex -> decimal: 72
[System.Text.Encoding]::UTF8.GetBytes('€') | ForEach-Object { $_.ToString('X2') }
Format-Hex .\notes.txt                            # hex dump of a file
```

## Remember
- ASCII is 7 bits, UTF-8 is backward compatible.
- Base64 and URL encoding hide nothing.
- Look-alike characters can fake domains.
