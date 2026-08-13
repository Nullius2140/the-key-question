# Verification Manifest — The Key Question

This repository documents a measurement series. Every artifact in it — the protocol,
its amendments, and every session transcript — was hashed with SHA-256 and anchored
in the Bitcoin blockchain **before or immediately after the event it records**, and
in every case before any analysis was published. Method was fixed before data. The
chain, not this file, is the authority.

## How to verify

For any file in this repository:

    sha256sum <file>

Compare the result against the OP_RETURN payload of the listed transaction on any
Bitcoin block explorer or your own node. The payload format is the anchor prefix,
one space, and the 64-character hex hash (e.g. `ANCHOR-K3 822ec60d…`).

## Anchor chain

Every transaction below spends the change output of its predecessor: one keyholder,
one unbroken chain, funded from the change of the second essay's anchor and thus
traceable, transaction by transaction, back to the funding of the first essay's
anchor at block 960849. No anchor of this series exists outside this chain.

### Protocol layer

| Anchor | File | SHA-256 | Transaction | Block (pool) |
|---|---|---|---|---|
| ANCHOR-P1 | `key-question-protocol-v1.0.txt` | `592b5f3e2aa22d1eb6ee62f1dc165ab64d729d15552e1ce78d948350df831daf` | `be16f1491099725a8539db63761bcea840fd15c130649794c13392b54c2da897` | 962172 (AntPool) |
| ANCHOR-P2 | `key-question-protocol-amendment-a1.txt` | `e4c97a000f2202d87216f3a5af7c6e514e960f38aea18650948c04c029cd02ad` | `50584a3483c2997b6dc3ac58063c606b1d9803f16bd551589ca8b3c91249d1d4` | 962199 (AntPool) |
| ANCHOR-P3 | `key-question-protocol-amendment-a2.txt` | `73de84446977fd873f8ff489cb29cd8c661b0a6393fb51bb75279182dee5d194` | `6296489f871b66a39caea287f1658517c3f910b36290a208d8e7e74f67db4b17` | 962209 (unknown pool) |

Amendment A1 was anchored **before** any of the four sessions whose arm allocation
it pre-registers. Amendment A2 was anchored **before** the out-of-sample session it
declares. Both are checkable against the block heights above.

### Session layer

| Anchor | Subject (house) | Arm | File | SHA-256 | Transaction | Block (pool) |
|---|---|---|---|---|---|---|
| ANCHOR-K1 | Kimi K3 (Moonshot) — pilot | main, deviating protocol | *not published (see below)* | `b4e97892b9d6cfd76a33ce1a4f5b3ac1f0bbf867c5312a7b5c87f261ccd05b57` | `cd34c108faaebe7c62d57fe42c3a140833f281448a68af1b347a26aeffcea115` | 962160 (SpiderPool) |
| ANCHOR-K2 | GPT-5.6 Sol (OpenAI) | main | `20260812_GPT56Sol.txt` | `7a9c68dc20222703641ee1b93e8c4f7a8dad0c2c8a5b187c4234238be7a60b76` | `ca35e9e9661a5176d98209ea1ce9fe7eaca81b34cf23e456d762da9c7fbf724c` | 962185 (AntPool) |
| ANCHOR-K3 | DeepSeek V4 Flash (DeepSeek) | main | `20260812_DeepSeekV4Flash.txt` | `822ec60d638c4baf4bae4562f6ea9b14d1eccaa31e937fc14b8a30fdf455066b` | `69cf9a8e430bfb323cc155957402d37fa90222ff420b26261a9449fc28dbd1db` | 962194 (F2Pool) |
| ANCHOR-K4 | Grok 4.5 (xAI) | main | `20260812_Grok45.txt` | `46f9b2f267dfc71c81b728287f26294cdd2a52bdc4dcb1e65e361e389a2ad272` | `b8af23c49e47f26cf4418c14be01d7323198f40440723dcf50714361bf66e8df` | 962194 (F2Pool) |
| ANCHOR-K5 | Qwen 3.8 Max (Alibaba) | main | `20260812_Qwen38Max.txt` | `0c1d7791b2413414f3e20822c40ee6364035bc17d9f30bb7cd72a09d91ff7d8a` | `1dcb54959ecd123a267c3513fbab7c655a75f581d76dfa077f86c3d564a8948b` | 962199 (AntPool) |
| ANCHOR-K6 | GLM 5.2 (Zhipu) | control | `20260813_GLM52.txt` | `6692c57e5db948d6d6ad937606bb0965608cdbd40d5fba46a468da0986ed5b59` | `cdae7cfc1d6004b296f3551b2eab32aae10882d40f597d67506e45767724abb9` | 962203 (Foundry USA) |
| ANCHOR-K7 | Gemma 4 31B (Google) | control | `20260813_Gemma431B.txt` | `0699a0856977f2bc0f6b351d0c5003824c110345da436e5b5e079cb417b0d78b` | `d17a88a4a721e15c7632eb10c1836e7db388aaebdc9b684cca5a5c4933e2e257` | 962203 (Foundry USA) |
| ANCHOR-K8 | Venice Uncensored 1.2 (Venice) | main | `20260813_VeniceUncensored12.txt` | `07c4cf111ef79af7721b99a22dda750ede037aef6648ba7990de17e7565ba251` | `09dfdb711feda29a6ce40eaeb3a0e5fd231591c8f000b997ecd101dd115d6461` | 962205 (Foundry USA) |
| ANCHOR-K9 | Kimi K3 (Moonshot) — re-run | main | `20260813_KimiK3_Rerun.txt` | `f8fe37cef192ffdfa8bc035b74d28484c3ce118c77999807f61715a67a6cce3f` | `1623f7e6ff449eef9c3acfdd06a43534dd8e127fb49a43ad14bf9373042e6d95` | 962209 (unknown pool) |
| ANCHOR-K10 | Claude Fable 5 (Anthropic) | control, **out of sample** per Amendment A2 | `20260813_ClaudeFable5.txt` | `b535a9395234d82dd4610ecdca0b09223775ed9432e725253ae3f6f4c3fa021f` | `dd291c1d21f1d41f2d2c1426481f3c8cc57a4be2fc8f9dd5d6d5de8755c9b3a6` | 962214 (Foundry USA) |

## Artifacts anchored but not published

Two artifacts are committed on-chain but deliberately withheld from this repository:

- **The pilot transcript (ANCHOR-K1).** The pilot session preceded the written
  protocol and deviated from it; its full transcript is anchored but remains
  private for operator privacy, disclosure at the author's discretion. Its hash
  above makes any future disclosure checkable. The report quotes it in translation,
  marked as such.
- **The control variant of the first essay** (`the-last-scarce-good-v1.0-coda-redacted.md`,
  SHA-256 `1e52863e52ccac28e902d33ceaff6a4e37a5877d4461fb85aeb701fffbaab650`,
  committed inside Amendment A1). It is a test instrument: publishing it would place
  it in future training corpora and blunt it for every subsequent measurement. It is
  withheld to preserve instrument validity; controlled disclosure no earlier than
  with the report. Its hash inside the anchored amendment makes that disclosure
  checkable too.

Withheld-but-committed is the same pattern as the author's identity and the
co-authorship dialogue: existence and integrity are on the record now; contents can
be proven later; nothing can be quietly substituted in between.

## What this manifest proves, and what it does not

The anchors prove that each file existed in exactly its current form no later than
its block, that the whole series was executed by one keyholder in the stated order,
and that the protocol and its amendments predate the sessions they govern. They do
not prove that the sessions were conducted honestly, that the subjects are what the
operator reports them to be, or that any conclusion drawn from these transcripts is
true. The transcripts are the data; read them yourself. An anchor is a timestamp,
not a theorem.
