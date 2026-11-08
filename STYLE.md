# STYLE.md: house style for files and docs

These are disciplines, not necessities. Their value is in keeping to them.

## Filenames

- **ASCII only**, and **legal in MS-DOS 5.0**: letters, digits and
  ``! # $ % & ' ( ) - @ ^ _ ` { } ~``. No spaces, no other punctuation.
- **Aim for 8.3**: up to eight characters, a dot, up to three. Don't obsess:
  `.java` is fine, `.markdown` is daft.
- **Extensions are usually lowercase** (`.txt`). A file *type* is usually
  the extension in capitals without the dot (TXT, MD), but sometimes a
  CamelCased name (Java). There's no hard rule for which.

## Content

- **Favor ASCII.** You need a reason to use UTF-8.

## Docs: MD and TXT

- **LLMs write prose as MD.** Humans write TXT in the first instance.
- **A TXT file is always a draft.** Humans' TXTs may contain mistakes, so
  read them critically and point mistakes out.
- **`moreMDs/`** holds finished MDs that don't need to be at the root.
- **`draftMDs/`** holds drafts that are meant to stay drafts for now. A TXT
  here is a draft by intent, not just by default.

## Structure

- The MDs **cross-refer as a single DAG** with `README.md` at the root: every
  MD is reachable from the README, and no chain of references loops back.
- **Keep `README.md` punchy.** Move content around the MDs freely, the root
  ones especially.
- Which MDs live at the root and which in `moreMDs/` is a judgement call.
  **At a dozen root files, it's time to shuffle.**
