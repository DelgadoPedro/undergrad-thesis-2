# Search

## Search string

As in the base study, the query has four blocks joined by AND. The first block was extended after a pilot (see below), and the phase block was changed to monitoring terms. The architecture and practice blocks are the same as in the base study.

```
MLOps AND Architect AND (Monitoring OR Observability OR Drift) AND (Practice OR Guideline OR Tactic OR Strategy OR Recommendation OR Pattern OR "Best Practice" OR Antipattern OR Smell OR "Technical Debt" OR Pitfall)
```

| Block | Terms |
| --- | --- |
| MLOps | `MLOps`; `"Machine Learning"` |
| Architecture | `Architect` |
| Phase | `Monitoring`; `Observability`; `Drift` |
| Practice | `Practice`; `Guideline`; `Tactic`; `Strategy`; `Recommendation`; `Pattern`; `"Best Practice"`; `Antipattern`; `Smell`; `"Technical Debt"`; `Pitfall` |

Google does not handle complex strings well, so the string was split into simple queries. Each query combines one term of each block, for example `MLOps Architect Monitoring Practice`. This gives 2 × 3 × 11 = 66 queries.

## Search settings

- Search engine: Google (`google.com`).
- Browser: Chrome, in an incognito window, to reduce personalized results.
- Location: Brazil, with no region or language settings.
- Dates: October 29 and 30, 2026.
- Stopping rule: the first two result pages of each query, as in the base study.
- Only organic results were counted. Ads, video carousels, and other result blocks were ignored.
- No limit on publication date.

Every result page was saved as HTML at the time of the search.

## Search pilot

The base study used a pilot to choose the abbreviation `MLOps` over the full term. A similar check was made here. Three pairs of queries were run, each in two versions, one with `MLOps` and one with `"Machine Learning"`. The top 20 organic results of each query were classified as promising or not from their title and snippet. The `"Machine Learning"` version found 25 promising results that the `MLOps` version did not, 53% more, above the 30% threshold set before the pilot. The two versions shared only seven results. The final search therefore ran all queries in both versions.

## Files

| File | Content |
| --- | --- |
| `queries.csv` | The 66 queries of the final search. |
| `html/` | The 132 saved result pages of the final search (66 queries × 2 pages). |
| `pilot_queries.csv` | The 6 queries of the search pilot. |
| `pilot_results.csv` | The 112 organic results of the pilot and their classification. |
| `html_pilot/` | The 12 saved result pages of the pilot. |

The results of each query, with their position, title, site, and snippet, are in `selection/selection.xlsx`, sheet `1_search_results`.

### `queries.csv`

| Column | Description |
| --- | --- |
| `query_id` | `Q01A`–`Q33B`. The number identifies the pair of phase and practice terms; `A` is the `MLOps` version and `B` the `"Machine Learning"` version. |
| `version` | `MLOps` or `Machine Learning`. |
| `phase_term`, `practice_term` | The terms of the phase and practice blocks. |
| `query` | The query as typed in Google. |
| `url_page1`, `url_page2` | Google URLs of the first and second result pages. |
| `html_page1`, `html_page2` | Saved HTML of each page. |
| `organic_results` | Number of organic results in the two pages. |

### `pilot_results.csv`

| Column | Description |
| --- | --- |
| `query_id`, `page`, `position` | Query and position of the result. |
| `title`, `site`, `display_url`, `url`, `snippet` | Result as shown by Google. |
| `promising` | `yes`, `unsure`, or `no`, judged from title and snippet. |
| `note` | Remark about the result. |
