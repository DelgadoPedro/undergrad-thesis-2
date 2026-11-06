# Synthesis

## Process

The synthesis followed the thematic analysis of the base study, in three steps: write each practice as a guideline, refine and organize the guidelines, and group them into categories with open card sorting.

1. **Coding.** The 844 accepted excerpts were coded inductively, in batches of sources. Each practice in an excerpt received one code, and new codes were added to the codebook as new practices appeared. This resulted in 1,545 codings grouped into 68 codes.
2. **Guideline statements.** The codes were merged into 45 guideline statements written in the imperative. Bad practices were rewritten as the matching good practices. Advice about a specific tool counted only if the tool name could be removed without losing a general lesson. For each statement, a description summarizes what the sources say, cites them by identifier, and quotes them briefly. A script checked that every cited identifier belongs to the sources of the statement and that every quote appears word for word in its excerpts.
3. **Refinement.** Two statements were removed. The first, on evaluating candidate models in shadow mode, is about evaluating a release, not about monitoring a deployed model. The second, on versioning data and models before investing in advanced monitoring, was considered peripheral, because it is about versioning rather than monitoring. The remaining 43 statements are the sub-guidelines.
4. **Two levels.** Closely related sub-guidelines were grouped under one guideline that names the architectural concern they share. This resulted in 15 guidelines.
5. **Card sorting.** Open card sorting grouped the guidelines into 5 categories.

The coding, the first version of the statements and descriptions, and the card sorting were done with the support of an LLM (Claude, by Anthropic, Opus 5.5 model). The author validated the first set of statements and refined it by hand, and reviewed the card sorting. The supervisor validated the final list of guidelines and categories.

## Counting and the Rule of Three

The support of a guideline is the number of different sources, not of excerpts. As in the base study, the Rule of Three was applied: a guideline or sub-guideline needed at least three sources to stay. Text copied word for word from another source counted only once. No guideline or sub-guideline was removed by this rule: each sub-guideline has 7 to 67 sources, and each guideline has 20 to 87. Six of the 68 codes have fewer than three sources; they were kept inside the sub-guideline that groups them.

The number of sources describes the corpus. It does not measure the importance of a practice or how common it is in the field.

| Category | Guidelines | Sub-guidelines | Sources |
| --- | ---: | ---: | ---: |
| A. Monitoring architecture and integration | 4 | 9 | 72 |
| B. Monitoring scope and signals | 2 | 8 | 95 |
| C. Telemetry, traceability and governance | 2 | 5 | 67 |
| D. Data and model quality monitoring | 3 | 10 | 96 |
| E. Alerting, diagnosis and response | 4 | 11 | 115 |

## Files

`synthesis.xlsx`:

| Sheet | Rows | Content |
| --- | ---: | --- |
| `summary` | 9 | Counts of the synthesis. |
| `1_coding` | 1,545 | One row per coding: an excerpt and the code it received. |
| `2_codebook` | 68 | The codes, their description, and their support. |
| `3_statements` | 45 | The initial guideline statements, with the codes they merge and whether they were kept. |
| `4_guidelines` | 43 | The final result: one row per sub-guideline, with its guideline, category, sources, and description. |
| `5_categories` | 5 | The categories and their support. |

### `1_coding`

| Column | Description |
| --- | --- |
| `excerpt_id`, `source_id` | Excerpt and source (`Sn-k`, `Sn`); the text is in `extraction/extraction.xlsx`. |
| `code` | Code from the codebook. |
| `counted` | `no` for the excerpt that copies another source word for word, which is not counted. |

### `2_codebook`

| Column | Description |
| --- | --- |
| `code`, `description` | Code and the practice it stands for. |
| `codings`, `sources` | Number of counted codings and of distinct sources. |
| `source_ids` | Sources of the code. |
| `sub_guidelines` | Sub-guideline(s) that contain the code. |

### `3_statements`

| Column | Description |
| --- | --- |
| `statement_id` | Working identifier of the statement. |
| `statement` | Statement text. |
| `codes`, `sources` | Codes merged in the statement and number of sources. |
| `status` | `kept` or `removed`. |
| `sub_guideline_id` | Final identifier, if kept. |
| `reason` | Reason, if removed. |

### `4_guidelines`

| Column | Description |
| --- | --- |
| `category_id`, `category` | Category. |
| `guideline_id`, `guideline`, `guideline_sources` | Guideline and its number of distinct sources. |
| `sub_guideline_id`, `sub_guideline`, `sub_guideline_sources` | Sub-guideline and its number of distinct sources. |
| `source_ids` | Sources of the sub-guideline. |
| `description` | Summary of what the sources say, with source identifiers and short quotes. |
