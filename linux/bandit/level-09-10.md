# Bandit Level 9 → Level 10

## Objective
Find the password in `data.txt`, stored in a human-readable string preceded by
several `=` characters.

## Commands Used
```bash
strings data.txt | grep "==="
```

## Solution
`data.txt` is a binary file containing mostly non-readable data. Use `strings` to
extract only human-readable text, then pipe to `grep` to filter for lines containing
`===`, narrowing it down to the password.

## Notes / Debugging
- `cat data.txt` produces garbled output — it's a binary file.
- `strings` extracts sequences of printable characters from any file, including binaries.
- Grepping for `===` was enough to isolate the relevant lines from the `strings` output.
- The output showed the password split across multiple lines with `=` prefixes —
  the last line `========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey` is the password.

## Password
```
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

## Screenshot
![Level 9 → Level 10 Complete](screenshots/level-09-10-complete.png)