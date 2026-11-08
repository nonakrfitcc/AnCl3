# STYLE.md: house style for files and docs

These are disciplines, not necessities. Their value is in keeping to them.

## Filenames

1. **ASCII only**, and **legal in MS-DOS 5.0**: letters, digits and
   ``! # $ % & ' ( ) - @ ^ _ ` { } ~``. No spaces, no other punctuation.
2. **Aim for 8.3**: up to eight characters, a dot, up to three. Don't obsess:
   `.java` is fine, `.markdown` is daft.
3. **Extensions are usually lowercase** (`.txt`). A file *type* is usually
   the extension in capitals without the dot (TXT, MD), but sometimes a
   CamelCased name (Java). There's no hard rule for which.
4. **Avoid case clashes** in the file tree. `Alice` and `alice` side by side
   need a reason. That isn't a hard rule either: the rule is to think.

## Content

1. **Favor ASCII.** You need a reason to use UTF-8.

## Docs: MD and TXT

1. **LLMs write prose as MD.** Humans write TXT in the first instance.
2. **A TXT file is always a draft.** Humans' TXTs may contain mistakes, so
   read them critically and point mistakes out.
3. **`moreMDs/`** holds finished MDs that don't need to be at the root. They
   carry the same authority as root files.
4. **`draftMDs/`** holds provisional MDs, where breaking changes are expected.
   A TXT here is a draft by intent, not just by default.
5. **Split by contingency.** The more provisional something is, the further
   out it lives. Drones' MDs flow: worms, then drafts, then rules. Record
   findings in worms first; drafts cite worms rather than copying them, so
   updating a draft often means updating its references. Move content
   inwards, into `moreMDs/` or the root, as it becomes dependable.
6. **Nonstream MDs may cite worms.** Linking into the wormstream is fine, and
   such links count as main links.

## Structure

1. The MDs' **main links form a single DAG** with `README.md` at the root:
   every MD is reachable from the README, and no chain of main links loops
   back.
2. **Favor inline references**, and mark which kind each one is. A DAG link
   reads **"refer to X for ..."** or **"(NB: X ...)"**, and says why the
   reader should follow it. Any other link, including one that loops back,
   reads **"see also X"**, and may say why.
3. **Number list items** rather than using bullets, so they can be referred
   to. Contrast the levels: numerals for top-level items, letters for items
   inside them, so a reference like "re 2b" is unambiguous. Markdown won't
   render lettered lists, so write nested items inline: "(a) ..., (b) ...".
4. **Keep `README.md` punchy.** Move content around the MDs freely, the root
   ones especially.
5. Which MDs live at the root and which in `moreMDs/` is a judgement call.
   **At a dozen root files, it's time to shuffle.**
