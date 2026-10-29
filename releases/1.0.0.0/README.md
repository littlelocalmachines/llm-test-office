# Release 1.0.0.0 — LLM Test Office introduction

The introduction to the LLM Test Office: why small local AI models, how the test engine is built, what we measure. **No model results yet**; the first results arrive with the common-test videos (the next release folders).

Video: [youtube.com/watch?v=N_w67eAU0T4](https://www.youtube.com/watch?v=N_w67eAU0T4)

| File | What it is |
|---|---|
| `TRANSCRIPT_EN.md` | English transcript (152 sentences), sealed |
| `TRANSCRIPT_TR.md` | Turkish transcript (the source text; sentence N = English sentence N), sealed |
| `FACTS.json` | Every number the video states, as data (numeric facts only; free-text notes are not published) |
| `seal-en/`, `seal-tr/` | SHA-256 manifest, Ed25519 signature, two RFC 3161 timestamps (FreeTSA, DigiCert) |
| `STERILIZATION.md` | Report of the automated scan for personal or internal information (0 findings) |

Seal fingerprints (SHA-256 of the sealed transcripts):

```
English  71b706dc22f7a70d6e74a161a73ef1c00e88adf5365f110825b0962d8fc04a14
Turkish  631684a6d65399948f593f01d04f196659349a3e3120d730d77a83fe24db9f00
```
Verification: [`../../VERIFY.md`](../../VERIFY.md).
