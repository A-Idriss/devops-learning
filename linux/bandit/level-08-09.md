# Bandit Level 8 → Level 9

## Objective
Find the only line of text in `data.txt` that occurs exactly once.

## Commands Used
```bash
sort data.txt | uniq --unique
```

## Solution
`data.txt` contains many duplicate lines. First pipe through `sort` to bring identical
lines adjacent to each other, then pipe through `uniq --unique` to print only lines
that appear exactly once.

## Notes / Debugging
- `uniq` only detects duplicates on **adjacent** lines — `sort` first is essential.
- `uniq` without flags merges duplicates but still prints one copy of each — not what we want.
- `uniq --unique` (or `-u`) prints **only** lines with no duplicates at all.
- `sort -u` alone won't work here — it removes duplicates but still prints one copy of each line, making it impossible to tell which was unique.
- The pipeline `sort | uniq -u` is a classic pattern worth remembering.

## Password
```
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

## Screenshot
![Level 8 → Level 9 Complete](screenshots/level-08-09-complete.png)