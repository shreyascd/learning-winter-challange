# Day 006 - Binary, hex and encodings (ASCII/UTF-8)

Phase 1 - Foundation - Computers & Networks | W01 - D6 | Sun 11 Oct 2026

## Number systems
Computers store everything as bits (0 or 1). Three bases show up all the time:
- **Binary (base 2)** - digits 0 and 1. One byte = 8 bits, values 0 to 255.
- **Decimal (base 10)** - what we use day to day.
- **Hexadecimal (base 16)** - digits 0-9 and A-F. Each hex digit is exactly 4 bits, so one byte = two hex digits. `0xFF` = 255.

Quick conversions:
- 72 in binary: 64 + 8 = 64 + 8 -> `01001000`. In hex: `0x48`.
- Each bit position is a power of 2: 128, 64, 32, 16, 8, 4, 2, 1.

## ASCII
ASCII is a 7-bit table mapping 128 characters to numbers 0-127.
- `A` = 65 = `0x41` = `01000001`
- `a` = 97 = `0x61`
- `0` (the digit zero) = 48 = `0x30`
- space = 32 = `0x20`
- newline = 10 = `0x0A`
- Lowercase and uppercase letters differ by one bit (32), which is why `A` and `a` differ only in bit 5.

Control characters (0-31 and 127) are not printable: newline, tab, carriage return, and the null byte (0).

## Extended ASCII and code pages
Old systems used the 8th bit for extra characters, but many incompatible code pages existed (CP437, Windows-1252). The same byte could mean different letters on different systems, which caused mojibake (garbled text).

## Unicode and UTF-8
Unicode gives every character a code point, written `U+XXXX`. For example `€` is `U+20AC`.
UTF-8 is the common way to store code points as bytes:
- ASCII characters use 1 byte, exactly as before (backward compatible).
- Other characters use 2, 3 or 4 bytes.
- Example: `€` (U+20AC) becomes three bytes `E2 82 AC`.
- Example: `é` (U+00E9) becomes `C3 A9`.

A decoder that assumes the wrong encoding shows garbage, and a file can be read differently by two tools.

## Encodings you will see in security work
- **Hex** - raw bytes, used in hex dumps and hashes.
- **Base64** - turns binary into printable text (A-Z, a-z, 0-9, +, /). It is **encoding, not encryption**: anyone can decode it.
- **URL encoding** - `%20` for a space, `%3C` for `<`. Used to hide payloads in web requests.
- **Unicode tricks** - homoglyphs (look-alike characters, for example Cyrillic `а` vs Latin `a`) can fake domain names.
- **Null bytes** - can truncate strings in old software, a classic attack trick.

## Questions to revisit
- Why does UTF-8 use a variable number of bytes, and how does the decoder know where a character ends?
- Why is base64 not a safe way to hide data?
