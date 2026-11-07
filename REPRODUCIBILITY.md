# Reproducibility and evidence limitations

**This repository cannot reproduce the paper's results.** It does not contain the engine.

The paper grades every result:

- **T1** — re-executed for the paper: the engine's test suite (114/114 on CPython 3.14.6) and its trusted-core fingerprint check.
- **T2** — recorded by an engine version that was retained (10 records).
- **T3** — recorded by an engine version that was not retained (41 records). This covers every result for adversarial testing, experiment planning and representation.

No T2 or T3 result has been independently reproduced. The engine requires CPython 3.14.x because its trusted-core fingerprint depends on Python bytecode.

The engine studied in the paper is identified by SHA-256 `d42d6a453c6a36482952ec8894c286e7bf033e8c32ec9ab1405584d2dc93a597`. It is held privately by the author.
