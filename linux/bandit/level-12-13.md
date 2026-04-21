# Bandit Level 12 → Level 13

## Objective
Recover the password from `data.txt`, which is a hexdump of a file that has been
repeatedly compressed using gzip, bzip2, and tar.

## Commands Used
```bash
mkdir /tmp/lvl12
cp data.txt /tmp/lvl12
cd /tmp/lvl12
xxd -r data.txt > data
file data
mv data data.gz && gunzip data.gz
file data
mv data data.bz2 && bunzip2 data.bz2
file data
mv data data.gz && gunzip data.gz
file data
tar xf data
file data5.bin
tar xf data5.bin
file data6
mv data6 data6.bz2 && bunzip2 data6.bz2
file data6
tar xf data6
file data8
cat data8
```

## Solution
1. Create a working directory in `/tmp` and copy `data.txt` there.
2. Use `xxd -r` to reverse the hexdump back to binary.
3. Use `file` after each step to identify the compression format.
4. Rename the file to match its format and decompress accordingly.
5. Repeat until `file` reports ASCII text, then `cat` for the password.

## Notes / Debugging
- `xxd -r` reverses a hexdump back to binary — without this nothing else works.
- `file` is essential at every step — the extensions are misleading or missing.
- Compression layers encountered: gzip → bzip2 → gzip → tar → tar → bzip2 → tar → ASCII.
- Files must be renamed to the correct extension before tools like `gunzip` will accept them.
- `2>/dev/null` can clean up noisy output if needed.

## Password
```
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```

## Screenshot
![Level 12 → Level 13 Complete](screenshots/level-12-13-complete.png)