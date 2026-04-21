# Bandit Level 11 → Level 12

## Objective
Decode the ROT13 encoded contents of `data.txt` to reveal the password.

## Commands Used
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

## Solution
`data.txt` contains text encoded with ROT13, a simple cipher that shifts every letter
by 13 positions. Use `tr` to translate each letter to its ROT13 equivalent.

## Notes / Debugging
- ROT13 shifts each letter by 13 places: `A→N`, `B→O`, `N→A` etc.
- Since the alphabet has 26 letters, applying ROT13 twice returns the original text —
  the same command both encodes and decodes.
- `tr 'A-Za-z' 'N-ZA-Mn-za-m'` broken down:
  - `A-Z` maps to `N-ZA-M` — uppercase letters shifted by 13
  - `a-z` maps to `n-za-m` — lowercase letters shifted by 13
- ROT13 is **not** encryption — it offers no real security, just basic obfuscation.

## Password
```
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```

## Screenshot
![Level 11 → Level 12 Complete](screenshots/level-11-12-complete.png)