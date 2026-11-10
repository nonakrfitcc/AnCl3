# BUNDLES.md: bundles in the wormstream (draft)

Provisional; breaking changes are expected. See also
[`../WORMS.md`](../WORMS.md) for the bundle rules in brief.

## 1. What a bundle is

1. A bundle is a worm that is a directory, holding files that belong
   together: `UTCworms/inYYYYMM/<by|BY>AUTHOR/DDHHMMSS.DIR/`.
2. **The extension is `.DIR`, in uppercase**, deliberately, so a directory
   stands out where files are the norm. It is the one place where an
   uppercase extension is the rule.
3. The timestamp is when the bundle was started. That one `DDHHMMSS`
   identifies the logical author action: the bundle and its closing worm,
   if any, are one act, and share it.
4. **Files inside may have any names.** Only the bundle's own name keeps to
   the wormstream's rules.

## 2. Dropping a bundle

1. **A bundle is meant to be dropped atomically**: every file in one commit.
2. That is often impossible in practice, for example when a tool adds one
   file per commit. Then **all adds must come before any use.**
3. **Use, not mention.** Using a file means depending on it: importing,
   building or running it. Citing it or linking to it is a mention, and a
   mention is acceptable before the bundle is closed, with caveats. One
   caveat: a mention mustn't present an open bundle as complete.

## 3. Closing a bundle

Items 1 to 3 tell a writer where to put a closing worm. Item 6 tells a
reader where a closing worm is valid. They don't conflict.

1. **A bundle dropped over several commits** is closed by a worm with **the
   same timestamp**, beside it: `DDHHMMSS.md`. Add it once the bundle is
   fully authored.
2. **A bundle dropped in one commit** needs no closing worm, but one is good
   practice. If there is one, it ideally goes inside the bundle's root rather
   than beside it, under the same name: `DDHHMMSS.DIR/DDHHMMSS.md`. The
   commit message is a useful place to record that the drop was atomic.
3. **The author needn't write the closing worm.** A commit message saying
   the bundle is done should prompt the operative drone to drop one in the
   right place, whichever of the two it is. That is editorship, not
   authorship (refer to [`ROLES.md`](ROLES.md), 2.5).
4. **Once a closing worm exists, the bundle is closed:** no files may be
   added to it. Until then, it may be used only once all its adds are in
   (see 2.2).
5. **A closing worm should list the bundle's files**, within reason, so any
   later addition shows up as not belonging.
6. **For readers: a closing worm is valid in either place**, beside the
   bundle or inside it. That is simply a fact. Inside is tidier on the face
   of it (tucked away, not hidden), but there may be good reasons not to add
   to the bundle's root, for example when the bundle is a copyset that
   should stay exactly as copied.
7. In plain ASCII order `DDHHMMSS.DIR` sorts before `DDHHMMSS.md`, so a
   listing shows a closing worm beside the bundle straight after it.
8. **Time.** A closing worm always has its bundle's timestamp, wherever it
   sits, because that timestamp identifies the one author action. Beyond
   each author's names being monotonic, the record must be true and fair
   (see also [`../WORMS.md`](../WORMS.md), Timestamps). A closing worm's
   body says when it was written, and by whom, and gives a true and fair
   account of the drop.

## 4. A bundle with no closing worm

1. **A bundle that needs a closing worm is formally open until its
   time-matching `.md` appears.**
2. It may become increasingly obvious that one isn't going to appear. When
   to wait, and when to raise it, is a judgement call, made by looking at
   the bundle's commit times so far. Raise it with `WARN:`, or `NB:` if it
   looks harmless (refer to [`COMMITS.md`](COMMITS.md), section 4).
3. A bundle with a closing worm in neither place may be: (a) held open
   deliberately, because it is incomplete; (b) left unclosed by mistake,
   since a human author may plausibly forget the closing worm; or (c)
   explained by a commit message instead, for example a single-commit drop
   that avoided adding a file to a copyset.

## 5. Commentary

1. Refer to [`TIERS.md`](TIERS.md), section 7, for git in general.
2. The wormstream is the source of truth about a bundle: its own files and
   its closing worm.

## 6. Open questions

1. Which other caveats apply to mentioning a file in an open bundle.

## Evidence

1. Refer to
   [`../UTCworms/in202611/BYjokede/10224837.md`](../UTCworms/in202611/BYjokede/10224837.md),
   section 6, for the conclusions behind this draft.
