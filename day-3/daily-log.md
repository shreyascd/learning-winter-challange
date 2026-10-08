# Daily log

## Day 003 - File systems, paths, extensions, archive formats
**Topic:** File systems, paths, extensions, archive formats

### 3 things learned
1. A file extension is only a label; the real type is in the file's first bytes (magic bytes).
2. Absolute vs relative paths, and Linux being case-sensitive, decide where commands actually point.
3. Archives can carry path traversal (zip slip) and zip bombs, so list them before extracting.

### 1 thing to revisit tomorrow
- How ext4 journaling and APFS copy-on-write each protect data after a crash.
