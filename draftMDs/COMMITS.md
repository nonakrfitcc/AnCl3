# COMMITS.md: what commit messages should contain (draft)

Provisional; breaking changes are expected. See also
[`TIERS.md`](TIERS.md), section 7, for how commentary is read.

## 1. The subject line

1. **Say what changed.**
2. **Append the principal reference**, except in trivial cases: the worm
   that best explains the change, such as a ruling or a finding. For
   example: `Add the Apache 2.0 licence; see ./BYjokede/10204542.md`.
3. **The path is relative to the current month**, `UTCworms/inYYYYMM/`, so
   it starts with the author folder. A full path isn't needed.
4. **Across a month's end**, within a fortnight or so, the same short form
   is fine: the `DD` in the name says which month was meant. A `DD` later
   than today's must be last month's.
5. **For much earlier months**, use `../inYYYYMM/AUTHOR/...`.

## 2. The body

1. **Formalities come first**:
   (a) any ruling behind the change, citing the worm that records it;
   (b) whether a bundle drop was atomic;
   (c) any override of a repo rule, as `CLAUDE.md` 5.3 requires.
2. **Then the rationale**, after a blank line. Rationales are welcome, and
   are often the most clarifying part.
3. **Where a blank line isn't possible**, as in a one-line message,
   separate the parts with ` /// `.
4. **Trailers go last**, as git expects, such as the `Co-Authored-By` and
   `Claude-Session` lines Claude sessions add.

## 3. Who writes it

1. **Whoever commits answers for the message.** A tool may draft one, but
   it is checked before it is committed.
2. **Owners in a hurry get a pass.**

## 4. Flags

1. **A flag is raised in the subject line** of a commit to the author's own
   wormstream folder. Any author can do that without extra permission.
2. **Only `FAIL:` leads.** Unless something failed, the action taken leads,
   and any other flag comes after it, before the `see ./...` reference.
3. **The flags, most urgent first:**
   (a) `FAIL:` a failure;
   (b) `WARN:` a warning;
   (c) `NB:` a downgraded warning: "I have to report this, but I've looked
   and I think it'll be okay." Downgrading is a judgement call, like a lint
   comment that suppresses a compiler warning;
   (d) `BTW:` feedback likely to be read with some attention;
   (e) `FYI:` feedback of less urgency;
   (f) `FTR:` for the record, likely to be skimmed or ignored: "Since that's
   false I'd better say so, but it clearly doesn't matter."
4. **So there are three kinds**: failures (a), warnings (b and c) and
   feedback (d to f).
5. **For example**: `FAIL: closing worm for 08101500.DIR not written; see
   ./byAlice/...`, or `Add notes on the relay; FYI: its docs are a week
   old; see ./BYjokede/...`.
6. **Drones watch commit subjects for flags**, and take them to an owner
   where needed.

## 5. Open questions

1. Whether and how to pin citations to git hashes. Set aside for now.

## Evidence

1. Refer to
   [`../UTCworms/in202611/BYjokede/10224837.md`](../UTCworms/in202611/BYjokede/10224837.md),
   section 5, for the conclusions behind this draft.
