# Next

Updated: 2026-11-22

## Where it stands

The receiver station for the Colloquy of Mobiles signal vocabulary: a webcam watching a phone torch, or a microphone hearing a gated tone, decodes the stream into one of eight dictionary words and relays every sample over a WebSocket; the matcher also runs headless in Node. It runs as a long-lived Node process with a `Procfile`. The last work (2 and 3 Sep 2026) rewrote the README to describe the receiver as it is and adopted the Virtual-Colloquy-of-Mobiles naming; the transmitter in `apps/transmitter/` is frozen, and the maintained one lives in the Virtual-Colloquy-of-Mobiles repository.

## Next step

Get the client type-check green, the first P1 item in the README's "Prioritised improvements". Fix the shadowed `count` in `src/client/renderer.ts` (around line 418) first, since it is a latent bug, then the unused locals and the `Uint8Array` variance errors that `npx tsc --noEmit` reports. CI runs this check first, so until it passes the server type-check and the tests never run there.

## After that

- Ship `config/` with the build, so deployed pages honor the config file (P1).
- Flatten the detector's inner loop: compute the background luminance frame once per tick (P1).
- The P2 and P3 items in the README's list, in order.

## Blocked or waiting

- None.

## Open questions

- The repository's website field points to a Vercel address that answers 404, while the README says this is not a Vercel site. Should the field point to where the receiver runs now, or be cleared?
- This plan was drafted by Claude on 2026-11-22 from the code and its history. Is the next step right?
