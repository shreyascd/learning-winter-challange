# Lab - Day 006: Convert 5 values by hand, verify with a Python one-liner

Rule: convert each value on paper first, then check it with the one-liner. Write your answer before running the check.

## Hand conversions
1. Decimal 72 -> binary: `__________` -> hex: `__________` -> character: `__________`
2. Hex 0x6C -> decimal: `__________` -> character: `__________`
3. Binary 01010111 -> decimal: `__________` -> character: `__________`
4. Character `y` -> decimal: `__________` -> hex: `__________` -> binary: `__________`
5. Character `€` -> code point (U+XXXX): `__________` -> UTF-8 bytes (hex): `__________ __________ __________`

## Python checks (run after writing your answers)
```bash
python3 -c "print(ord('y'), hex(ord('y')), bin(ord('y')))"
python3 -c "print(bin(72), hex(72))"
python3 -c "print(chr(0x6C))"
python3 -c "print(int('01010111', 2), chr(int('01010111', 2)))"
python3 -c "print(hex(ord('€')), '€'.encode('utf-8').hex(' '))"
```

## Results
- Did every hand answer match Python? Which one did I get wrong, and why?
- Output of the checks (paste):
```
(paste real output here)
```

## Screenshots to add
- [ ] Handwritten or typed answers for the 5 conversions
- [ ] Terminal output of the 5 Python checks

## Notes
- Which conversion took longest by hand?
- What did I confuse: 0 as a digit vs 0 as a value?
