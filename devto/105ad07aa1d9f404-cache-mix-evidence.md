# Claude Code token mix: retained local usage summary

This is a sanitized summary of a local usage note recorded on 19 August 2026. The note says its source was the `usage` fields in Claude Code assistant messages from 13 local profiles. Raw conversation logs are private and are not included here.

| Usage bucket | Tokens reported |
| --- | ---: |
| Cache reads | 61.65 billion |
| Fresh input | 1.31 billion |
| Cache creation | 2.18 billion |
| Output | 0.362 billion |
| **Total, rounded** | **65.5 billion** |

The four reported buckets sum to **65.502 billion** before rounding. Cache reads are **61.65 / 65.502 = 94.12%**, or **94.1%** to one decimal place. This percentage describes token volume in this local report. It is not a share of actual spend, a model benchmark, or an estimate for other users.

The retained note labels these numbers “30-day totals,” but it also describes log coverage from 18 July through 19 August, with 33 distinct days. The precise filtering script and per-day inclusion ledger were not retained with this summary. For that reason the accompanying article does not assert an exact calendar window or claim that this audit has been independently reproduced from raw logs. The published table supports its arithmetic and scope, not the extraction step.

[Anthropic's usage documentation](https://platform.claude.com/docs/en/api/rate-limits) explains that total input is `input_tokens + cache_creation_input_tokens + cache_read_input_tokens`; `input_tokens` alone is the uncached portion after the last cache breakpoint. Output tokens are a separate field. Any metered cost model needs each bucket's applicable rate. This local token summary contains no actual vendor bill or full build cost and cannot choose a build-versus-buy winner.
