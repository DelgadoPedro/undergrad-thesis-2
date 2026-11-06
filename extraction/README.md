# Extraction

## Process

As in the base study, the extraction took from each included source the text chunks that describe practices. For each source, the excerpts that describe monitoring practices were recorded word for word. When present, the nearby sentences that say when the practice applies or what it costs were kept with the excerpt. An optional note records remarks about the excerpt, such as the section it comes from. Practices that apply only to LLMs or generative AI were not extracted.

The extraction was supported by an LLM (Claude, by Anthropic, Opus 5.5 model, high reasoning effort). The LLM pre-selected candidate excerpts from the text of each source, and every excerpt was checked word for word against the source. The procedure was first tried on the 20 sources of the Phase B pilot, which the author also extracted independently; the two extractions were similar. No agreement measure was computed. Some pages blocked automated access; the author saved these pages, and their excerpts were taken from the saved copies.

## Validation

The candidate excerpts were then checked against fixed written rules. An excerpt was rejected when it contained only:

| Rule | Rejected when the excerpt is only | Excerpts |
| --- | --- | ---: |
| R1 | A definition or explanation | 110 |
| R2 | A list of metrics or statistical tests, with no design decision | 9 |
| R3 | A feature of a tool, with no general lesson | 32 |
| R4 | Motivation or marketing | 52 |
| R5 | Content outside the scope (retraining internals, deployment strategy, one-off pre-deployment test) | 14 |
| R6 | A practice specific to LLMs or agents | 3 |

An excerpt was accepted when it described a practice that affects the structure of the system or one of its quality attributes, for example where monitoring components sit, what to record, how alerts are routed, how monitoring triggers retraining, rollback or fallback, how delayed labels are handled, or a cost or latency trade-off.

The author reviewed the validated excerpts. Sources left with no accepted excerpt were excluded from the review (see `selection/selection.xlsx`, sheet `3_full_text`).

| Step | Excerpts |
| --- | ---: |
| Candidate excerpts | 1,064 |
| Rejected | 220 |
| Accepted | 844 |
| Accepted text copied word for word from another source, counted once | 1 |
| **Excerpts used in the synthesis** | **843** |

## Context of use and trade-offs

The 517 accepted excerpts with expressions of condition or cost (such as "when", "depending on", "at scale", "trade-off", or "overhead") were also reviewed to record the context of use or the trade-off they state, if any. Each one was given a short group label. This information was used only to enrich the descriptions of the guidelines.

## Files

`extraction.xlsx`:

| Sheet | Rows | Content |
| --- | ---: | --- |
| `summary` | 9 | Counts of the extraction. |
| `excerpts` | 1,064 | Every candidate excerpt, with its validation and its context of use or trade-off. |
| `validation_rules` | 7 | The rejection rules and the acceptance rule. |

### `excerpts`

| Column | Description |
| --- | --- |
| `excerpt_id`, `source_id` | Identifiers in the selection sheets (`IDn-k`, `IDn`). |
| `final_excerpt_id`, `final_source_id` | Identifiers used in the synthesis and in the thesis (`Sn-k`, `Sn`). Empty for rejected excerpts and for sources that were later excluded. |
| `quote` | Excerpt, word for word. `[...]` marks omitted text. |
| `note` | Remarks, such as the section of the source. |
| `validation` | `accepted` or `rejected`. |
| `rejection_rule` | `R1`–`R6`, if rejected. |
| `counted_once` | Marks the accepted excerpt that copies another source word for word. |
| `context_group`, `context` | Group label and text of the context of use stated in the excerpt, if any. |
| `trade_off_group`, `trade_off` | Group label and text of the trade-off stated in the excerpt, if any. |
