# v4 baseline — with vs without the skill (Hume case)

- `runner-control.md`: control input (no skill), frozen before any control run (`manifest.json`).
- `run-control-*-raw.md`: control outputs, verbatim, one per configuration.
- `blind-scoring-prompt.md`: the only file given to the blind scorer (G). Six paragraphs: three controls and the three skill Balanced variants from v3, bold removed, order shuffled (seed 20261109).
- `blind-key.json`: which paragraph is which. Do not give to the scorer.
- `protocol.md`: design and measures.

Known blinding leak: the skill's Balanced variants are 181–210 words, the controls 278–313, so length may reveal the condition.
