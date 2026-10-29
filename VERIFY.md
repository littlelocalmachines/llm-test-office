# How to verify

Three independent checks, from cheapest to strongest:

1. **The seal** — the files are exactly the files we published on the sealed date (checksums, signature, two timestamps).
2. **The scorer** — the published raw answers really get the published scores (re-score them, no model needed).
3. **The run** — the same model file, the same engine and the same invoices give you the same answers (re-run it).

You need `sha256sum`, `ssh-keygen` (OpenSSH ≥ 8.0) and `openssl` (≥ 1.1) for step 1, Python ≥ 3.11 for steps 2–3 (tested on 3.11 and 3.14), and 7-Zip (or any unzip tool that supports AES-256) to open `package.zip`. Password: `llm-test-office`.

## 1. The seal

Every sealed folder has `MANIFEST.sha256`, `MANIFEST.sha256.sig` and a `damga/` folder ("damga" = timestamp) with two RFC 3161 timestamp replies. Sealed folders:

| Folder | What it seals |
|---|---|
| `releases/1.0.0.0/seal-en/`, `seal-tr/` | Introduction video: English and Turkish transcripts and fact list |
| `releases/1.1.1.1/seal-tr/` | Group 1 video: Turkish transcript and fact list (sealed 2026-10-21, before translation and voice-over) |
| `releases/1.1.1.1/`, `releases/1.1.1.2/` | The whole release folder: results, model cards, `package.zip`, everything listed in its `MANIFEST.sha256` |

Run these inside the sealed folder (example: `releases/1.1.1.1`):

```bash
# 1a. files match the manifest
sha256sum -c MANIFEST.sha256

# 1b. the manifest was signed by our key
ssh-keygen -Y verify -f ../../keys/allowed_signers -I asgard-muhur -n asgard-boggart-muhur -s MANIFEST.sha256.sig < MANIFEST.sha256

# 1c. the manifest existed at the stated time (two independent authorities)
cd damga
openssl ts -verify -data ../MANIFEST.sha256 -in MANIFEST.digicert.tsr -CAfile ca_paket.pem
openssl ts -verify -data ../MANIFEST.sha256 -in MANIFEST.freetsa.tsr -CAfile freetsa_cacert.pem -untrusted freetsa_tsa.crt
openssl ts -reply -in MANIFEST.digicert.tsr -text | grep "Time stamp"
```

Expected: every line of 1a ends in `OK`; 1b prints `Good "asgard-boggart-muhur" signature …`; 1c prints `Verification: OK` twice. For a `seal-en/` or `seal-tr/` folder, the path to the key is one level deeper: `../../../keys/allowed_signers`.

`asgard-muhur` and `asgard-boggart-muhur` are the signer identity and signature namespace fixed when the first seals were made; they are names, not secrets. OpenSSL may warn that the FreeTSA signing certificate "is not a CA cert"; that is normal for a timestamp certificate.

The fingerprint printed in each video description is the SHA-256 of that video's sealed `MANIFEST.sha256`:

```bash
sha256sum releases/1.1.1.1/seal-tr/MANIFEST.sha256
# b16ec34351c9229c8274f5a388cc9bc26c6b1b2dc5a1fb1b08103da8b734e826
```

**What a valid seal proves:** these exact files existed, unchanged, no later than the timestamp, and were signed by the holder of the key in `keys/allowed_signers`. **What it does not prove:** that the measurements are right. That is what steps 2 and 3 are for.

## 2. Re-score the raw answers (no model needed)

```bash
cd releases/1.1.1.1
7z x -pllm-test-office package.zip -opkg
cd pkg
python -m llm_test_office.yeniden_puanla data/noisy_rows.jsonl
python -m llm_test_office.yeniden_puanla data/clean_r2_rows.jsonl
```

For every model and engine it prints the stored pass count, the re-scored pass count and the number of rows that disagree. Expected: 0 disagreements. Any disagreement is a bug on our side; please open an issue.

## 3. Re-run a model

See `RERUN.md` in each release folder: the exact commands, the model files (with SHA-256) and what to expect.
