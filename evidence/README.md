# Claim-evidence inventory

Every number below comes from retained analysis or qualification artifacts inspected for this portfolio. The two JSON files are sanitized excerpts, not full source artifacts. Figures are rendered from these excerpts. Private source paths and the internal audit mapping are kept outside this public folder.

## Sportsbook evidence S1

**Source:** [sportsbook-aggregates.json](sportsbook-aggregates.json), excerpted from a retained completed calibration analysis. Its `source_sha256` identifies the inspected aggregate file; `raw_export_sha256` identifies the private raw input. Raw data were not reconstructed for this build.

| Claim | Backing fields | Meaning | Important caveat |
|---|---|---|---|
| 7,722 captured opportunities | `census.raw`, `census.unique` | Raw count and unique retained opportunity count agree | Captures, not bets or profit |
| 5,248 valid closing observations | `census.usable` | Observations eligible under the close rule | Missing-close selection may bias results |
| 873 event clusters | `census.clusters` | Event/game dependence units in usable data | Not proof that every event is statistically independent |
| 2,471 missing; 3 invalid closes | `census.missing_close`, `census.invalid_close_window` | Mutually excluded rows in retained reconciliation | 7,722 = 5,248 + 2,471 + 3 |
| 80/20 split; 698/175 clusters | `method.split`, `split` | Chronological event-level calibration/holdout allocation | Opportunity counts are not split 80/20 |
| 5,000 resamples; 95% intervals; 20-minute close rule | `method` | Retained bootstrap and close-validity protocol | Portfolio does not rerun private-data estimation |
| 18 changed-schedule clusters; 285 observations | `schedule_changes` | Schedule changes handled within canonical event clusters | No individual event IDs are disclosed |
| Holdout table and CLV plot | `pooled.holdout`, `pooled.calibration` | Mean CLV and bucket-wise event-bootstrap intervals | CLV is not ROI; bucket event counts overlap |
| 677 props; 9 moneyline; zero NBA holdout observations | `holdout_composition` | Retained holdout composition | Narrow transferability across sports and markets |

The retained analysis also reports that provider fair-price freshness was unavailable. Public extraction omits candidate floors, granular proprietary diagnostics, and event-level identifiers.

## Novig evidence S2–S6

**Source:** [novig-aggregates.json](novig-aggregates.json). Source digests identify corpus qualification (S2), freeze record (S3), frozen specification (S4), compressed evaluation output (S5), and evaluation qualification (S6). These artifacts remain private. The full specification contains withheld research definitions.

| Claim | Backing fields | Meaning | Important caveat |
|---|---|---|---|
| 70,598 observed executions; 85 games | `observed_market_executions`, `canonical_games` | Market taker-execution observations and canonical sporting games | Not personal trades or eligible inferential N for every test |
| 46,992 pregame; 23,606 later | `pregame_executions`, `at_or_after_start_executions` | Partition by scheduled start | The headline corpus includes both partitions |
| Retained observation bounds and acquisition dates | `observed_window_utc`, `acquisition_date_counts` | Earliest/latest execution times and acquisition-file totals | Five acquisition dates do not imply full uninterrupted coverage or five independent game-date groups |
| 12 candidates plus one control; 13 freeze entries | `candidate_hypotheses`, `diagnostic_controls`, `freeze_total_entries` | Distinguishes survivor-eligible hypotheses from the control | Internal freeze, not external registry registration |
| Frozen before outcomes | `frozen_before_outcome_evaluation_recorded`, `frozen_spec_lf_sha256` | Recorded pre-outcome protocol and retained hash match | The record is not independent attestation of researcher access history |
| Zero survivors | `survivors`, `candidate_decisions` | All 12 candidate decisions are KILL | Historical discovery only; no universal absence-of-effect claim |
| Side-control effects at 60/300/900 seconds | `control_effects` | Equal-game mean oriented execution-price movements in pp | No midpoint, confidence interval, fill, or return claim |

Build checks matched the frozen specification hash after CRLF-to-LF normalization and matched both compressed and decompressed evaluation hashes to S6. Full-resolution control values are retained; displayed values round to three decimals. The corpus and raw executions were not regenerated. Private features, candidate definitions, exact thresholds, and per-game records are excluded.

## Engineering evidence E1–E6

These are **implementation-inspected** claims rather than externally reproducible production qualification. Private source digests are recorded in the internal inventory. No production source is distributed.

| Reference | Inspected owner/evidence class | Supported property | Boundary |
|---|---|---|---|
| E1 | Read-only exchange stream client and mocked transport regressions | Local snapshot/delta ladders, shared continuity, timestamps, bounded fixed-subscription reconnects | Subscription-ID routing, per-ticker resnapshot barriers, and independent trade-sequence checks are not demonstrated |
| E2 | Continuity state machine and its regressions | Before-snapshot gating, sequence-gap invalidation, snapshot recovery, terminal retry exhaustion | Missing sequences cannot establish gap detection |
| E3 | Recorder, normalized schema, and outcome-orientation tests | Canonical event/outcome binding, provenance, stream-versus-poll distinction | A venue timestamp does not identify network latency or causality |
| E4 | Create-only recorder persistence and interrupted-run tests | Retention without prior-run overwrite | Best-effort line parsing is weaker than lossless sealed evidence |
| E5 | Lifecycle evidence store and durable ownership implementation | Content-addressed payloads, sealed manifest integrity, persisted fences and acquisition claims | No claim of measured live availability or uniform adoption across the system |
| E6 | Pure lifecycle state semantics and authoritative-state adapter | Finality distinct from pending/settled terminal status | Research semantics do not settle sportsbook balances |

Test descriptions refer to inspected regression definitions. A passing historical qualification record is noted for the Novig study; this is not a claim that production live operation was validated during portfolio assembly.

## Screenshots

**Source:** pre-existing desktop and mobile research-page visual-test artifacts, copied unchanged. The associated test definition captures the authenticated application rather than constructing a design mockup. The build did not rerun that authenticated capture.

**Meaning:** actual UI appearance and its manual research/empty-state language. **Important caveat:** no independent capture timestamp, current production-state assurance, test-pass assurance, active markets, actual trades, or performance evidence is inferred. [Captions and images](../architecture/README.md#selected-ui-captures)

## Independent inspection boundary

A reviewer can inspect aggregate counts, exclusions, units, splits, the negative outcome, and data underlying the figures. Source digests bind the selected evidence to privately retained artifacts; they do not supply private data or prove a result by themselves. Full reproduction, external preregistration attestation, and production qualification are outside this public evidence package. No unsupported candidate headline was used.
