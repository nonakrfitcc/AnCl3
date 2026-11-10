# SECRETS.md: what never goes in (draft)

Provisional; breaking changes are expected. See also
[`PARADIGM.md`](PARADIGM.md) for why: nothing committed can be hidden
later, so secrets are kept out at the door.

## 1. Never commit

1. Private keys of any kind, Nostr `nsec...` keys included.
2. Tokens, passwords and API keys, and `.env` or similar files that hold
   them.
3. Anything else secret, sensitive or legally actionable.

## 2. If a secret gets in

1. Tell an owner at once.
2. The only remedy is to rotate the secret. History is not rewritten to
   remove it.

## 3. Public and private

1. **AnCl3 is public; AnCl9, its sister, is private.** The split will
   become legally significant in time, but not yet.
2. **So AnCl3 takes no transcripts yet**, and drones keep their working in
   AnCl9 and publish only their conclusions here. See also
   [`../CLAUDE.md`](../CLAUDE.md), 0.4 and 3.5.

## 4. Open questions

1. Redaction rules, which will come with transcription.
2. What the public/private split will mean once it becomes legally
   significant.

## Evidence

1. Refer to
   [`../UTCworms/in202611/BYjokede/10224837.md`](../UTCworms/in202611/BYjokede/10224837.md),
   section 1, for the conclusions behind this draft.
2. See also [`../CLAUDE.md`](../CLAUDE.md), section 4, the operative rule
   from which sections 1 and 2 are drawn.
