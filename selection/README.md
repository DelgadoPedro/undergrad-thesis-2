# Selection

## Process

1. **Deduplication.** The 66 queries returned 1,223 organic results. Duplicates were removed by comparing the normalized title and the domain of each result, because the saved result pages encode most links as redirects and do not show the final address. Pages with the same title on different sites were kept as separate sources. Three duplicates were only found in later phases and were then merged into the matching source. After deduplication, 609 unique sources remained.
2. **Phase A: title and snippet.** Each source was screened by its title and by the snippet shown by Google. Only sources that clearly met an exclusion criterion were excluded. In case of doubt, the source went on to Phase B. Phase A excluded 435 sources and left 174.
3. **Phase B: full text.** Each remaining source was opened in an incognito window. Its final address and access date were recorded, and its full text was assessed against all the criteria. Phase B excluded 51 sources and left 123 included sources, identified as S1–S123.

Each phase started with a pilot, reviewed with the supervisor to clarify the criteria. The Phase A pilot used 31 random sources (5% of 609, rounded up). The Phase B pilot used 20 of the sources that passed Phase A.

| Step | Sources |
| --- | ---: |
| Organic results | 1,223 |
| Duplicates removed | 614 |
| Unique sources | 609 |
| Excluded in Phase A | 435 |
| Read in full text | 174 |
| Excluded in Phase B | 51 |
| Included | 123 |

## Criteria

A source was included if it met IC1 and none of the exclusion criteria. One exclusion criterion was enough to exclude it.

| ID | Criterion |
| --- | --- |
| IC1 | The source describes at least one architecturally significant practice (good or bad) for monitoring or observability of MLOps systems. |
| EC1 | The source is not in English. |
| EC2 | The source is an advertisement or an introduction to another source (e.g., a full course or a commercial tool). |
| EC3 | The source is in a multimedia format (video, podcast, or slides). |
| EC4 | The source is a scientific paper, a preprint, a thesis, or a dissertation rather than practitioner material. |
| EC5 | The full text cannot be read in an incognito window without login or payment. |
| EC6 | The source is mainly about monitoring or observability of LLMs, foundation models, or generative AI applications. |
| EC7 | The source is not about ML or MLOps systems. |
| EC8 | The source is about ML or MLOps systems, but not about the monitoring or observability of the MLOps system in operation. |
| EC9 | The source is about ML monitoring, but describes no architecturally significant practice. |

A practice is architecturally significant when it affects the structure of the system and its key quality attributes, such as scalability, maintainability, performance, security, and reliability. Advice about a specific tool counts only if the tool name can be removed without losing a general lesson. A vendor page written mainly to sell or present a product is excluded under EC2; vendor content that describes a practice is kept.

EC1–EC5 come from the base study. EC6 follows from the exclusion of LLM-focused sources from the scope. The base study used three inclusion criteria; here they were merged into IC1, and their negations became EC7–EC9, so that every exclusion has a specific reason.

| Criterion | Phase A | Phase B |
| --- | ---: | ---: |
| EC1 | 1 | 0 |
| EC2 | 12 | 7 |
| EC3 | 7 | 0 |
| EC4 | 165 | 1 |
| EC5 | 5 | 7 |
| EC6 | 13 | 1 |
| EC7 | 92 | 0 |
| EC8 | 124 | 15 |
| EC9 | 16 | 20 |
| **Total** | **435** | **51** |

## Files

`selection.xlsx` has one sheet per step. `included_sources.csv` is a copy of the last sheet.

| Sheet | Rows | Content |
| --- | ---: | --- |
| `summary` | 7 | Number of sources at each step. |
| `1_search_results` | 1,223 | Every organic result, with the unique source it belongs to and whether it is a duplicate. |
| `2_screening` | 609 | Phase A decision for each unique source. |
| `3_full_text` | 174 | Phase B decision for each source read in full text. |
| `4_included` | 123 | Final list of included sources. |
| `criteria` | 10 | Inclusion and exclusion criteria, with notes. |

### `1_search_results`

| Column | Description |
| --- | --- |
| `result_id` | `R1`–`R1223`, in the order the queries were run. |
| `query_id`, `page`, `position` | Query (see `search/queries.csv`), result page, and position on the page. |
| `title`, `site`, `snippet` | Result as shown by Google. |
| `retrieved_at` | Date and time the result page was saved. |
| `source_id` | Unique source the result belongs to. |
| `status` | `unique` for the first result of each source, `duplicate` for the others. |
| `note` | Reason for the duplicate. |

### `2_screening`

| Column | Description |
| --- | --- |
| `source_id`, `title`, `site`, `snippet` | Source as shown by Google. |
| `pilot` | `yes` if the source was part of the Phase A pilot. |
| `decision` | `to full text` or `excluded`. |
| `criterion` | Exclusion criterion, if excluded. |
| `justification` | Short reason for the decision. |

### `3_full_text`

| Column | Description |
| --- | --- |
| `source_id`, `title`, `site` | Source. |
| `url`, `access_date` | Final address of the page and date it was read. |
| `pilot` | `yes` if the source was part of the Phase B pilot. |
| `decision` | `included` or `excluded`. |
| `criterion`, `justification` | Exclusion criterion and reason, if excluded. |
| `note` | Remarks, e.g. sources excluded during extraction because no excerpt was valid. |
| `final_id` | `S1`–`S123` for included sources. |

### `4_included`

| Column | Description |
| --- | --- |
| `final_id` | `S1`–`S123`, the identifiers used in the thesis. |
| `source_id` | Identifier in the previous sheets. |
| `title`, `publisher`, `url`, `access_date` | Source. |
| `publisher_type` | Type of publisher, used to describe the corpus. |
| `excerpts` | Number of excerpts used in the synthesis. |
