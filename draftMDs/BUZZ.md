# BUZZ.md: linking AnCl3 to the Buzz relay (draft)

Provisional. Breaking changes are expected. This is the working picture for
issue #2, the link between AnCl3 and the Buzz relay at `buzzyb.ot-mo.de`.

## Current picture

1. **One channel per issue**, plus one feed channel for the repo. Buzz gives
   an agent one session per channel, so one issue becomes one bee session.
2. **The feed channel is also the repo's channel.** Buzz requires a repo to be
   bound to a channel, and reading the repo requires membership of it.
3. **Bees use a key per session**, which the owner vouches for through
   Buzz's NIP-OA, so each new bee doesn't need admitting by hand.
4. **Budget is ours to enforce.** Buzz has no spend cap, so each session gets
   one.
5. **The GitHub-to-relay link is ours to build:** bees push `main` to both.

## Open questions

1. How the owner signs a NIP-OA tag for each session's key, in practice.
2. Whether Buzz's git hosting is robust enough to mirror into yet.
3. What starts a bee session when an issue is labelled.

## Evidence

Refer to
[`../UTCworms/in202611/BYjokede/08130507.md`](../UTCworms/in202611/BYjokede/08130507.md)
for the research behind this picture: Buzz's docs and source, our relay's
responses, and existing practice elsewhere.
