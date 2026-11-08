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
| `AUTHOR` | Who wrote it: a Claude session's handle, or a human's self-assigned handle (see below). |
| `DDHHMMSS` | The UTC day, hour, minute and second the file was written. |
| `.EXT` | The file type, or `.DIR` for a bundle (see below). |

Examples:

```
UTCworms/in202611/BYjokede/07225519.md
UTCworms/in202611/BYkoa584/08091500.py
UTCworms/in202611/byAlice/08101200.md
UTCworms/in202611/by123456/08101300.txt
UTCworms/in202611/byAlice/08101500.DIR/notes.txt
```

The prefix is chosen to contrast with the name. Digits and capitals are
full-height, so lowercase `by` reads more easily before them, and uppercase
`BY` before a lowercase name.

## Authors

1. **Claude sessions** use a handle derived from the six-character nonce at the
   end of the session's branch name: the letters in order, then the digits in
   order (`5k8o4a` gives `koa584`); see also [`CLAUDE.md`](CLAUDE.md) for the
   rule in full. Each conversation gets its own handle, which keeps authors
   from colliding.
2. **Humans** use a handle they assign themselves, such as `Moanak`
   (`byMoanak`).

## Timestamps

1. All times are UTC. The month directory and the filename come from the same
   instant.
2. Names only need to be **unique** and **monotonic**: a greater name means a
   later file. The exact second doesn't matter.
3. If the name is already taken, or isn't greater than the author's latest
   file, bump the seconds (and carry into minutes and so on) until it is.

## Extensions

Keep to 8.3: `DDHHMMSS` is already eight characters, so extensions have at
most three (`.md`, `.txt`, `.c`, `.h`, `.py`, `.htm`, ...). Use a longer one
only when a toolchain demands it, as `.java` does.

## Bundles

A worm can also be a **bundle**: a directory named `DDHHMMSS.DIR` holding a
group of files that belong together.

1. **`.DIR` is uppercase on purpose**, so a folder stands out where files are
   the norm.
2. **A bundle drops as a group** and is closed once written: nothing is ever
   added to it later. Bees commit the whole bundle in one commit. A human whose
   tools add one file per commit may add them in a short run of consecutive
   commits, and the bundle is closed when that run ends.
3. **Files inside** may have any names that keep to 8.3. Refer to
   [`STYLE.md`](STYLE.md) for the other filename rules they must follow.
4. **The timestamp** is when the bundle was started.

## What's fixed and what isn't

1. **Under `UTCworms/`: write once.** To correct or extend a worm, write a new
   one that refers to it.
2. **Root files** (`README.md`, `CLAUDE.md`, `WORMS.md`, `.gitignore`, ...) may
   be updated.
3. Rules evolve, so older worms won't always match the latest rules. That's
   expected. Don't "fix" them.
4. Everything is committed straight to `main`. No branches.
