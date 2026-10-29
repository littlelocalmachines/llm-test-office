# Corrections policy

1. **Videos are never deleted.** A wrong measurement stays online.
2. The title gets **[CORRECTED]**, and a pinned comment shows the old and new result side by side with the **root cause** (for example: "the wrong chat template was applied to model X").
3. **`ERRATA.md`** records every correction: date, video, affected number, old → new value, root cause, reporter (if they agree) and the seal of the corrected run.
4. The re-measurement uses the **same model card**; only the faulty field changes, and the changed field is marked.
5. Reporters are credited if they wish, in `ERRATA.md` and the pinned comment.
6. **Sealed raw records are never edited.** A correction is a new sealed run; the old one stays and is marked "replaced by".
7. Report problems through issues: "wrong template", "broken quantization", "parser rejected an answer unfairly", "fact list and narration disagree".
8. A correction that does not change the result is still recorded ("no effect").
