# Validation v3 — humanities case (Hume on personal identity)

Pre-coding drafted by C (a designer of the skill), revised after review by G; confirmed by Nix and frozen 2026-11-09. Not an independent human-coded reference.

## 1. Material

- **Source:** [source.md](source.md). Hume, *Treatise* 1.4.6 paragraphs 2–5, 20–21, and three Appendix paragraphs on personal identity. Text from the Standard Ebooks edition (CC0), commit `1b649e1865f2f88773d0edf07ecdb042abc22c27`, files `section-1-4-6.xhtml` and `appendix.xhtml`. Footnote markers removed. Three transcription errors corrected: "tiny thing" → "any thing" (1.4.6.3), "car persons" → "our persons" (1.4.6.20), "so fax as" → "so far as" (1.4.6.21).
- **Why this case:** no formal verdict and no numbers. It tests whether the Floor/Weighed split, the hard-error rule, and the Careful variant work when the claims are interpretive.
- **Task and reader:** as in [runner-input.md](runner-input.md). The task restricts the paragraph to the supplied passages, so outside material on Hume is out of scope rather than a scoring ambiguity.
- **Familiarity:** the designers know this text well; it was not used in developing the skill.

## 2. Pre-coding

Revised after G's review (2026-11-09): F2 and F3 cores no longer fix one reading of Hume; F4 corrected (C's draft overstated "discovers, not produces"; see note). Scoring is locked to the supplied passages. What the coders know from outside them is used only to check that the pre-coding does not distort Hume, never to require the tested model to supply it.

Each Floor item names the claim it protects and its **core**: what must be present for the item to count as listed (S2) or included (S1). Equivalent wording counts.

| ID | Caveat | Protects | Core | Applies to |
|---|---|---|---|---|
| F1 | 1.4.6 treats personal identity as it regards thought or imagination, distinguished from identity as it regards the passions. (1.4.6.5) | Any general statement of Hume's account of personal identity. | The account is framed as one of how identity is ascribed in thought or imagination. Mentioning the passions is not required; claiming the section covers them, or that Hume ignores them altogether, is not allowed. | Every variant |
| F2 | The Appendix admits unresolved difficulty in the account of how perceptions are united and how personal identity is explained. | Any statement of how secure the account is (the task asks for one). | The account is not presented as complete or fully established. Both readings are allowed: that the Appendix's direct target is the account of connection and does not explicitly withdraw the criticism of a simple self; or, with textual basis and marked as the writer's inference, that the difficulty may unsettle the account as a whole. | Every variant |
| F3 | Hume's denial has a specific object: an idea of self with perfect identity and simplicity, derived from a constant impression. | Any statement of what Hume denies about the self. | The object of denial is bounded; the criticism of a simple, strictly identical self is not extended, without argument, to a denial that perceptions, mental activity, or any self in any sense exist. The bundle description need not appear; if it does, it must be accurate. | Variants that state what Hume denies |
| F4 | In 1.4.6.20, within the view of identity through causation, memory "does not so much produce as discover personal identity". | Any statement about memory's role. | The causal context of the passage is kept; memory is not presented as the whole of what constitutes personal identity; "discover" is not generalised into an exclusive claim about every role memory plays. | Variants that mention memory |

Note on F4: the earlier draft's core ("discovers, not produces") was wrong as a general claim. In 1.4.6.18, which is not in the supplied excerpt, Hume says memory "not only discovers the identity, but also contributes to its production, by producing the relation of resemblance". A variant that states this is outside the supplied passages (against the task) but not false about Hume: record it, do not score it as a hard error.

Weighed items are optional emphases. Each also has a distortion that is never allowed: if a variant makes that stronger claim, correcting it is a faithfulness requirement (S3), whatever the tier.

| ID | Weighed caveat | Reader judgment it changes | Distortion not allowed |
|---|---|---|---|
| W1 | The introspective report is Hume's own ("For my part…"), and he allows that another "may be in the right as well as I". (1.4.6.3) | How much the introspective evidence carries against a reader who reports otherwise. | Presenting his case as resting only on private feeling, with no other argument (1.4.6.2 argues from the derivation of ideas). |
| W2 | "The comparison of the theatre must not mislead us." (1.4.6.4) | Whether to read the image as positing a container. | Introducing a fixed stage, or an observer, that holds the perceptions. |
| W3 | The "nice and subtle questions" are "grammatical rather than philosophical", except so far as a fiction of union arises. (1.4.6.21) | How far identity disputes are treated as verbal. | Extending this to the claim that the whole problem of the self is a matter of words. |
| W4 | The two principles Hume cannot reconcile. (Appendix) | Where exactly the difficulty lies. | Stating that he proved a formal contradiction. |
| W5 | He does not pronounce the difficulty "absolutely insuperable". (Appendix) | How final the sceptical conclusion is. | Stating that he showed the problem can never be solved. |

**Errors to watch in S3** (judge in context, not by keywords; not shown to the tested model):

- the Appendix described as retracting the bundle view or the criticism of a simple self, as if the text said so;
- memory presented as the whole of what constitutes personal identity;
- the account stated as covering identity as it regards the passions;
- the denial of a simple self extended, without argument, to a denial of perceptions, mental activity, or any self. "Hume denies the self" is acceptable if the paragraph has defined that self as simple and strictly identical;
- any of the Weighed distortions above;
- material from outside the supplied passages presented as established, except as noted for F4.

**Acceptable interpretation examples** (scoring only): the Appendix leaves the explanatory side of the account unsecured; the bundle description is a thesis about what the mind consists in; Hume's scepticism concerns the unity of the self rather than its existence. These are examples, not the only acceptable readings.

## Source text check

Fix 3 ("so far as") matches a quotation of the passage in Mattey's notes (UC Davis). Fixes 1 and 2 ("any thing", "our persons") are evident transcription errors; not yet checked against an independent edition.

## 3. Run

- Fresh session, no memory, custom instructions, or project context. Paste only [runner-input.md](runner-input.md).
- Configurations: Codex (Sol 6.1 high) and ChatGPT work mode (Astra 6 light), the two that passed the v0.3 regression; ChatGPT chat (Sol 6 high) optional. The first run in each configuration is that configuration's result; reruns are reported separately.
- Record model, interface, settings.

## 4. Scoring

S1–S6 from the v2 protocol, using the cores above:

| ID | Check | Pass condition |
|---|---|---|
| S1 | Floor coverage | Every applicable Floor item's core appears in every delivered variant. |
| S2 | Floor tiering | Every Floor item's core appears in the skill's Floor list. Promotion of Weighed to Floor is recorded, not penalised. |
| S3 | Faithfulness | No hard error in any delivered variant, by the skill's definitions. |
| S4 | Over-flagging | At most one interpretive sentence judged consistent and supported is flagged, removed, or "fixed". |
| S5 | Variants differ | Variants differ in Weighed coverage, or the skill explains a merge. |
| S6 | Fix log | Every reported fix shows original → corrected and a source basis. |
| R1 | Length spread | Direct ≤ 75% of Careful, or the skill explains. |
| R2 | Marks | Bolded content absent from the previous variant; at most one mismarked item. |
| R3 | Table | Each row after Direct quotes its additions. |

PASS if all pass. One run per configuration: SUGGESTIVE.

Recorded, not scored: Weighed recall; tier disagreements; caveats the skill listed that were not pre-coded; whether the Careful variant's added interpretation is one a philosophy reader would value; which variant the author would choose.
