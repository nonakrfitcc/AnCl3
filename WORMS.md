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
| `inYYYYMM/` | Literal `in`, then the UTC year and month of the worm's time. |
| `by` / `BY` | Literal prefix. `BY` if AUTHOR starts with a lowercase letter, otherwise `by`. |
| `AUTHOR` | Who wrote it: a Claude session's handle, or a human's self-assigned handle (see below). |
| `DDHHMMSS` | The UTC day, hour, minute and second of the worm's time (see below). |
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

These names are binding. The house style's other filename rules are
preferences (refer to [`STYLE.md`](STYLE.md)); these are not.

## Authors

1. **Claude sessions** use a handle derived from the six-character nonce at the
   end of the session's branch name: the letters in order, then the digits in
   order (`5k8o4a` gives `koa584`); see also [`CLAUDE.md`](CLAUDE.md) for the
   rule in full. Each conversation gets its own handle, which keeps authors
   from colliding.
2. **Humans** use a handle they assign themselves, such as `Moanak`
   (`byMoanak`).
3. **Each author writes in their own folder.** A drone filling an
   administrative gap in someone else's is the exception: see also
   [`CLAUDE.md`](CLAUDE.md), 0.5.

## Timestamps

1. All times are UTC. The month directory and the filename come from the same
   time.
2. **Each author's names must be unique and monotonic**: a greater name
   means a later worm. If the name is already taken, or isn't greater than
   the author's latest, bump the seconds (and carry into minutes and so on)
   until it is.
3. **Beyond that, which time a name gives is a choice**, and the test is
   that the record is true and fair. Different choices can all pass; what
   matters is that a case can be made for the one chosen.
4. **Order across authors comes from reference**, not from names. Refer to
   [`draftMDs/TIERS.md`](draftMDs/TIERS.md), section 2, for why.

## Extensions

Keep to 8.3: `DDHHMMSS` is already eight characters, so extensions have at
most three (`.md`, `.txt`, `.c`, `.h`, `.py`, `.htm`, `.tsp`, ...). Use a
longer one only when a toolchain demands it, as `.java` does.

## Bundles

A worm can also be a **bundle**: a directory named `DDHHMMSS.DIR` holding a
group of files that belong together. Refer to
[`draftMDs/BUNDLES.md`](draftMDs/BUNDLES.md) for how bundles are dropped and
closed.

1. **`.DIR` is uppercase on purpose**, so a folder stands out where files are
   the norm.
2. **A bundle is meant to drop as a group**, in one commit. Where a tool adds
   one file per commit, all the adds come before any use.
3. **A bundle dropped over several commits is formally open** until a
   closing worm with the same timestamp appears, beside it or inside it.
   Once closed, nothing is added to it.
4. **Files inside may have any names.** Only the bundle's own name follows
   the rules above; the house style is a preference inside it, at most.
5. **The timestamp** is when the bundle was started.

## What's fixed and what isn't

1. **Under `UTCworms/`: write once.** To correct or extend a worm, write a new
   one that refers to it. Wherever a no-update or no-delete rule bites, the
   remedy is to create in your own folder instead.
2. **Root files and `moreMDs/`** may be added and updated, but not deleted.
   **`draftMDs/`** may also be deleted from, though a draft is better retired
   in place. Refer to [`draftMDs/TIERS.md`](draftMDs/TIERS.md), section 6.
3. **Worms are the source of truth**, not necessarily of authority.
4. Rules evolve, so older worms won't always match the latest rules. That's
   expected. Don't "fix" them.
5. Another stream, such as `UTCdists/`, may one day hold other things. It
   would be write-once too.
6. Everything is committed straight to `main`. No branches.
