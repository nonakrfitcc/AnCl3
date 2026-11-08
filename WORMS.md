# WORMS.md: the wormstream

This repo is WORM: **write once, read many**. Everything authored here goes
into the wormstream under `UTCworms/` as new files. Nothing in it is ever
edited, renamed, moved or deleted.

## Layout

```
UTCworms/inYYYYMM/<by|BY>AUTHOR/DDHHMMSS.EXT
```

| Part | Meaning |
|---|---|
| `UTCworms/` | Literal. The root of the wormstream. |
| `inYYYYMM/` | Literal `in`, then the UTC year and month the file was written. |
| `by` / `BY` | Literal prefix. `BY` if AUTHOR starts with a lowercase letter, otherwise `by`. |
| `AUTHOR` | Who wrote it: a Claude session's handle, or a human's username (see below). |
| `DDHHMMSS` | The UTC day, hour, minute and second the file was written. |
| `.EXT` | The file type. |

Examples:

```
UTCworms/in202611/BYjokede/07225519.md
UTCworms/in202611/BYkoa584/08091500.py
UTCworms/in202611/byAlice/08101200.md
UTCworms/in202611/by123456/08101300.txt
```

The prefix is chosen to contrast with the name. Digits and capitals are
full-height, so lowercase `by` reads more easily before them, and uppercase
`BY` before a lowercase name.

## Authors

- **Claude sessions** use a handle derived from the six-character nonce at the
  end of the session's branch name. The rule is in [`CLAUDE.md`](CLAUDE.md).
  Each conversation gets its own handle, which keeps authors from colliding.
- **Humans** use their username.

## Timestamps

- All times are UTC. The month directory and the filename come from the same
  instant.
- Names only need to be **unique** and **monotonic**: a greater name means a
  later file. The exact second doesn't matter.
- If the name is already taken, or isn't greater than the author's latest
  file, bump the seconds (and carry into minutes and so on) until it is.

## Extensions

Keep to 8.3: `DDHHMMSS` is already eight characters, so extensions have at
most three (`.md`, `.txt`, `.c`, `.h`, `.py`, `.htm`, ...). Use a longer one
only when a toolchain demands it, as `.java` does.

## What's fixed and what isn't

- **Under `UTCworms/`: write once.** To correct or extend a worm, write a new
  one that refers to it.
- **Root files** (`README.md`, `CLAUDE.md`, `WORMS.md`, `.gitignore`, ...) may
  be updated.
- Rules evolve, so older worms won't always match the latest rules. That's
  expected. Don't "fix" them.
- Everything is committed straight to `main`. No branches.
