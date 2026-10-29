# Sterilization report

- Files scanned: 105
- Rules: 13 text rules + entropy + 10 binary-metadata markers + zip-content scan
- Findings: **0**
- Documented exceptions: 15


## Documented exceptions

| File | Rule | Reason |
|---|---|---|
| keys/allowed_signers:1 | iç sistem adı | Seal-verification signer identity (asgard-muhur) was fixed when the seals were made; changing it means re-sealing (owner decision pending). |
| releases/1.0.0.0/seal-en/damga/MANIFEST.freetsa.txt:35 | e-posta (noreply dışı) | Subject field of FreeTSA's public certificate (third party, public information); not ours. |
| releases/1.0.0.0/seal-tr/damga/MANIFEST.freetsa.txt:35 | e-posta (noreply dışı) | Subject field of FreeTSA's public certificate (third party, public information); not ours. |
| releases/1.1.1.1/damga/MANIFEST.freetsa.txt:35 | e-posta (noreply dışı) | Subject field of FreeTSA's public certificate (third party, public information); not ours. |
| releases/1.1.1.1/package.zip!llm_test_office/kos.py:3 | yerel uç | Default endpoint of the public runner: LM Studio's factory port 1234 on the reader's own machine, same for every user; not our proxy (9504). |
| releases/1.1.1.1/package.zip!llm_test_office/kos.py:109 | yerel uç | Default endpoint of the public runner: LM Studio's factory port 1234 on the reader's own machine, same for every user; not our proxy (9504). |
| releases/1.1.1.1/RERUN.md:45 | yerel uç | Re-run command shows LM Studio's factory endpoint 127.0.0.1:1234 on the reader's own machine; not our proxy (9504). |
| releases/1.1.1.1/seal-tr/damga/MANIFEST.freetsa.txt:35 | e-posta (noreply dışı) | Subject field of FreeTSA's public certificate (third party, public information); not ours. |
| releases/1.1.1.2/damga/MANIFEST.freetsa.txt:35 | e-posta (noreply dışı) | Subject field of FreeTSA's public certificate (third party, public information); not ours. |
| releases/1.1.1.2/package.zip!llm_test_office/kos.py:3 | yerel uç | Default endpoint of the public runner: LM Studio's factory port 1234 on the reader's own machine, same for every user; not our proxy (9504). |
| releases/1.1.1.2/package.zip!llm_test_office/kos.py:109 | yerel uç | Default endpoint of the public runner: LM Studio's factory port 1234 on the reader's own machine, same for every user; not our proxy (9504). |
| releases/1.1.1.2/RERUN.md:45 | yerel uç | Re-run command shows LM Studio's factory endpoint 127.0.0.1:1234 on the reader's own machine; not our proxy (9504). |
| VERIFY.md:28 | iç sistem adı | The ssh-keygen namespace (asgard-boggart-muhur) was fixed at signing time and must appear in the verification command (owner decision pending). |
| VERIFY.md:37 | iç sistem adı | The ssh-keygen namespace (asgard-boggart-muhur) was fixed at signing time and must appear in the verification command (owner decision pending). |
| VERIFY.md:39 | iç sistem adı | The ssh-keygen namespace (asgard-boggart-muhur) was fixed at signing time and must appear in the verification command (owner decision pending). |

Result: **PASS** — no personal or internal information found by these rules.
