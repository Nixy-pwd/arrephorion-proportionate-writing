# Which configuration to run it in

The skill asks for several steps in one response: list caveats, write three variants as separate wholes, mark differences, check each against the source. Configurations differ in how reliably they follow all of these. Results below are for skill v0.3.

## Recommendation

| Configuration | Recommendation | Why |
|---|---|---|
| Codex, Sol 6.1, high | **Use** | No content errors on either material; variants rewritten as wholes and marked; reported fixes traceable. |
| ChatGPT work mode, Astra 6, light | **Use** | Same as Codex; the only configuration to pass every check on both materials. |
| ChatGPT chat, Sol 6, high | **Not recommended** | Built later variants by appending sentences to earlier ones on both materials, did not mark differences, and made the only content error observed with v0.3. |

Evidence level: SUGGESTIVE. One run per configuration per material, two materials. Model and interface vary together, so these results say which configurations worked, not whether the model or the interface is responsible. That the lightest model, in work mode, did best suggests the interface matters (PLAUSIBLE).

## Results

| | Codex, Sol 6.1 high | Work mode, Astra 6 light | Chat, Sol 6 high |
|---|---|---|---|
| Content errors, Gate record (technical decision) | 0 | 0 | 0 |
| Content errors, Hume (humanities interpretation) | 0 | 0 | 1: memory's role stated as exclusive ("discovers, not produces") |
| Variants rewritten as wholes | Yes, both | Yes, both | No, both (later variant = earlier one plus appended sentences) |
| Differences marked | Yes (1 missed mark on each material) | Yes | No marks received on either material¹ |
| Length spread, Direct/Careful | 0.61, 0.43 | 0.63, 0.44 | 0.70, 0.50 |
| Protocol result, Gate | PASS | PASS | FAIL |
| Protocol result, Hume | FAIL on one tier-listing check² | PASS | FAIL |

¹ The chat outputs were copied from the web interface; whether bold formatting was lost in copying is unverified.
² The check required a conditional caveat (memory) to appear in the Floor list; every memory statement was accurate. See [validation/v3-case/result-codex.md](validation/v3-case/result-codex.md) for why this check is mis-specified.

Detailed scoring: [validation/v2-case/](validation/v2-case/) (Gate record, v0.3 regression files) and [validation/v3-case/](validation/v3-case/) (Hume).

## If you use another configuration

Check one output for three things before relying on it:

1. **Are the variants rewritten?** If the longer variant starts with the shorter one word for word, the configuration is appending, and the extra content may not read continuously.
2. **Are the differences marked in bold?** If not, compare the variants yourself before choosing.
3. **Are paraphrases of the source as strong as the source?** Look for comparisons turned into absolutes ("not so much X as Y" → "not X") and verdicts restated more strongly or weakly than stated.
