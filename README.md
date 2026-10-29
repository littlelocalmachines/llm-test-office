# Little Local Machines — LLM Test Office

Small local AI models, measured on one ordinary computer, offline, on office documents. Our test engine and our measurements are public: **take them and check them.**

This repository holds everything behind the numbers in our videos: the test engine you can run yourself, every raw model answer, the results computed from them, and a cryptographic seal (SHA-256 manifest, two independent RFC 3161 timestamps, an Ed25519 signature) proving the sealed files did not change after the date on the seal.

**Don't trust the video — verify it, or re-run it.** → [`VERIFY.md`](VERIFY.md)

## Releases

| Release | Video | What is in it |
|---|---|---|
| [`1.0.0.0`](releases/1.0.0.0/) | [Introduction](https://www.youtube.com/watch?v=N_w67eAU0T4) | Why small local models, how the engine works. Sealed EN + TR transcripts, fact list. No model results. |
| [`1.1.1.1`](releases/1.1.1.1/) | [Common test, group 1](https://www.youtube.com/watch?v=BdjfpzVzEiw) | MiniCPM 5 1B, Gemma 3 1B, Llama 3.2 1B, SmolLM2 1.7B. Results, raw answers, engine, sealed TR transcript. |
| [`1.1.1.2`](releases/1.1.1.2/) | Common test, group 2 (video not out yet) | LFM2 1.2B, LFM2.5 1.2B, Qwen3 1.7B. Results, raw answers, engine. |

Each test release folder has `README.md` (what the video found), `RESULTS.md` + `results.csv` (every number, computed from the data), `MODELS.json` (model files and their SHA-256), `HARDWARE.json`, `FACTS.json` (every number the video states), `RERUN.md` (how to run it yourself) and `package.zip`.

## `package.zip` and its password

The engine, the generated invoices and every raw model answer are inside `package.zip`, encrypted with AES-256.

**Password: `llm-test-office`** (the same for every release).

The password is not a secret. It only keeps web crawlers and training-data collectors from swallowing the test set: a test set that leaks into a model's training data stops measuring anything. Please do not republish the unzipped files.

## What the common test is — and what it is not

The invoices in the common test are **synthetic**. The common test exists to meet every model under the same conditions: the same prompt, the same invoices with known correct answers, no help from our software. Model-specific software, harder tests and real documents belong to the model-specific test process, which has its own releases.

"Noisy" invoices are the same synthetic invoices with simulated scanner errors (character confusions such as `0`→`O`, `1`→`l`, `5`→`S`); no digit is ever changed to a different digit.

## How we keep it fair

- **Same engine, same prompt for every model.** Temperature 0, thinking off, the same 200 invoices (generator seed 42).
- **Every number is computed, not typed.** `RESULTS.md` is generated from the raw data in `package.zip`, and generation stops if any number differs from the number said in the video.
- **Negative results are not verdicts.** A model that does not pass has only shown how it performs in this test system, with this data and this way of working.
- **Sealed results are never edited.** A new run is a new release; the old one stays with its old fingerprint.

## Independence

1. No sponsor or model maker sees, changes or approves tests or results before publication.
2. Sponsored segments, if any, are marked on screen and in the description and are separate from the test.
3. All hardware was bought by us. Hardware sent to us in the future will be disclosed at the start of the video; the sender has no say.

## Corrections

Found a mistake? Open an issue. Confirmed errors go into [`ERRATA.md`](ERRATA.md) with their root cause; videos are never deleted. See [`CORRECTIONS_POLICY.md`](CORRECTIONS_POLICY.md).

## Licenses

Test engine: PolyForm Noncommercial 1.0.0 · data, results, text and visuals: CC BY-NC 4.0. Tested models keep their own licenses; this repository does not redistribute model weights. Details: [`LICENSE.md`](LICENSE.md).

---

## Türkçe özet

Küçük yerel yapay zekâ modelleri, sıradan tek bir bilgisayarda, çevrimdışı, ofis belgeleri üzerinde ölçülüyor. Test motorumuz ve ölçümlerimiz herkese açık: **alın, kontrol edin.** Her test sürümünde motor, bütün ham model cevapları, bunlardan hesaplanan sonuçlar ve mühür (SHA-256 manifest, iki bağımsız RFC 3161 zaman damgası, Ed25519 imza) var.

`package.zip` parolası: **`llm-test-office`** (her sürümde aynı). Parola gizli değildir; yalnız tarayıcı botların ve eğitim verisi toplayıcıların test kümesini yutmasını önler.

Ortak testteki faturalar **sentetiktir**: amaç bütün modelleri aynı istemle, doğru cevabı bilinen aynı faturalarla tanımaktır; modele yazılım desteği yoktur. Modele özel yazılım, zorlu sınamalar ve gerçek belge özel test sürecindedir. Doğrulama: [`VERIFY.md`](VERIFY.md).
