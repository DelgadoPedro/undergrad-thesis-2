# Architecturally Significant Guidelines for Monitoring in MLOps Systems

Supplementary material of the undergraduate thesis *Architecturally Significant Guidelines for Monitoring in MLOps Systems* (Pedro Delgado, ICMC-USP, 2026).

The study is a Gray Literature Review (GLR). It replicates the method of Amou Najafabadi et al. (2026), *Architecturally Significant MLOps Guidelines for ML Model Integration and Deployment: a Gray Literature Review* ([arXiv:2606.06535](https://arxiv.org/abs/2606.06535)), with the scope changed from model integration and deployment to monitoring.

**Research question.** What are common architecturally significant guidelines for monitoring in MLOps systems?

**Result.** 15 guidelines, detailed by 43 sub-guidelines and organized into 5 categories, derived from 843 excerpts of 123 gray literature sources.

## Contents

| Folder | What it contains |
| --- | --- |
| [`search/`](search/) | Search string, the 66 queries, the search pilot, and the saved Google result pages (HTML). |
| [`selection/`](selection/) | All search results, deduplication, the two selection phases, the criteria, and the final list of sources. |
| [`extraction/`](extraction/) | The extraction form: every candidate excerpt, its validation, and the context of use or trade-off it states. |
| [`synthesis/`](synthesis/) | Coding, codebook, initial guideline statements, and the final guidelines with their sources and descriptions. |

Each folder has its own README that explains the step and the columns of its files.

## Numbers at a glance

| Step | Count |
| --- | ---: |
| Queries | 66 |
| Organic results | 1,223 |
| Unique sources after deduplication | 609 |
| Sources read in full text | 174 |
| Included sources | 123 |
| Candidate excerpts | 1,064 |
| Excerpts used in the synthesis | 843 |
| Codings / codes | 1,545 / 68 |
| Sub-guidelines / guidelines / categories | 43 / 15 / 5 |

## Identifiers

- `R1`–`R1223`: search results, one per organic result of a query.
- `IDn`: unique sources after deduplication. Numbers are not contiguous, because a few IDs were merged into others as duplicates.
- `S1`–`S123`: included sources. These are the identifiers used in the thesis.
- `Sn-k`: excerpt `k` of source `Sn`. Numbers are not contiguous, because rejected excerpts keep their number.
- `A1`–`E4`: guidelines; `A1.1`–`E4.4`: sub-guidelines.

## Use of an LLM

An LLM (Claude, by Anthropic, Opus 5.5 model) supported the extraction, the first version of the guidelines, and the card sorting. Every excerpt was checked word for word against its source. The author supervised and reviewed each step, and the supervisor validated the final list of guidelines and categories. Details are in [`extraction/`](extraction/) and [`synthesis/`](synthesis/).

## Base study

The replication package of the base study is available at Zenodo: [10.5281/zenodo.19284709](https://doi.org/10.5281/zenodo.19284709).
