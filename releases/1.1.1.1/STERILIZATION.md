# Sterilization report

- Files scanned: 25
- Rules: 13 text rules + entropy + 10 binary-metadata markers + zip-content scan
- Findings: **0**
- Documented exceptions: 4


## Documented exceptions

| File | Rule | Reason |
|---|---|---|
| package.zip!llm_test_office/kos.py:3 | yerel uç | Default endpoint of the public runner: LM Studio's factory port 1234 on the reader's own machine, same for every user; not our proxy (9504). |
| package.zip!llm_test_office/kos.py:109 | yerel uç | Default endpoint of the public runner: LM Studio's factory port 1234 on the reader's own machine, same for every user; not our proxy (9504). |
| RERUN.md:45 | yerel uç | Re-run command shows LM Studio's factory endpoint 127.0.0.1:1234 on the reader's own machine; not our proxy (9504). |
| seal-tr/damga/MANIFEST.freetsa.txt:35 | e-posta (noreply dışı) | Subject field of FreeTSA's public certificate (third party, public information); not ours. |

Result: **PASS** — no personal or internal information found by these rules.
