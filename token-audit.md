# A retained Claude Code log slice, checked by message ID

Audited 27 September 2026. This is an aggregate-only summary of private local JSONL files. It does not publish conversation content or message IDs.

An older local note reported 65.502 billion tokens across 13 Claude Code profiles and called the result a 30-day total. Its stated July 18–August 19 dates span 33 calendar days. The original extraction script and its per-day inclusion ledger were unavailable. The currently retained archive cannot reproduce that estate-wide figure: only two of the 13 profile directories have assistant usage rows in the stated date filter, with the first retained rows on August 5 and 6.

| Currently retained rows matching July 18–August 19 | Count |
| --- | ---: |
| Assistant usage rows | 116,158 |
| Distinct `message.id` values | 53,231 |
| Four-bucket token sum over every row | 16,578,476,984 |
| Four-bucket sum, one final row per message ID | 8,287,399,574 |
| Cache-read tokens in the unique-message sum | 7,994,753,110 |

The raw-row total is **2.0004 times** the unique-message total in this retained two-profile slice. Of the 53,231 IDs, 39,657 occur on multiple rows and 21,515 have changing output counters. Five anonymized repeated-ID checks found output counters rising while the other usage buckets stayed constant. For each ID the audit kept the row with the largest `output_tokens`, breaking a tie by latest timestamp. Selecting the latest row gave the same aggregate here. The cache-read share of the unique-message token volume is **96.47%**. It is not a share of actual spend.

To check a usage export, group assistant rows by `message.id`, inspect repeated groups, define a final-row rule, then sum each selected row's `input_tokens`, `cache_creation_input_tokens`, `cache_read_input_tokens`, and `output_tokens` once. [Anthropic's usage documentation](https://platform.claude.com/docs/en/api/rate-limits) defines the three input fields and their total-input equation. Nested cache-creation detail is a breakdown, so the audit does not add it again.

This slice cannot validate the old 65.502-billion total, its 94.1% cache-read share, an exact 30-day estate-wide window, or a model benchmark. The private archive may have changed since the old note was written; an error in that note's original extraction is also possible. These aggregate results cannot distinguish the two explanations. They do show why row identity and retention must be checked before using a token total in a cost or capacity comparison.
