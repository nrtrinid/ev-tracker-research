# Reliability and provenance

Evidence is useful only if its identity, timing, and failure history survive long enough to inspect. The properties below belong to specific research components, not to every subsystem uniformly. [Engineering backing notes](../evidence/README.md#engineering-evidence-e1e6) identify the inspection scope.

| Property | Implemented concept | Boundary |
|---|---|---|
| Frozen experiment inputs | Corpus manifests, specification hashes, deterministic generation, and immutable first-observed calibration entries | Public aggregates do not reproduce private raw inputs or hidden feature definitions. |
| Source provenance | Provider-local identity, source/receive times, payload references, transformation versions, and proven canonical bindings | Missing timestamps or sequence capabilities are explicit; they are not reconstructed as facts. |
| Append-only evidence | The simple recorder creates a new run and appends observations without replacing prior runs | Best-effort parsing is weaker than an integrity-qualified archive; malformed lines may be skipped. |
| Sealed canonical evidence | The lifecycle store content-addresses raw payloads, persists envelopes before derivation, and seals segments with chained manifests | Corrupt, unsealed, or inconsistent canonical evidence fails integrity validation; this is a separate component from the simple recorder. |
| Durable campaign ownership | Persisted campaign fences and exclusive acquisition claims reject stale or duplicate ownership | This describes repository behavior, not a claim of fault-free collection or measured availability. |
| Explicit terminal states | Pending finality, terminal settlement, and acquisition failure remain distinguishable | A final sporting result alone is not equivalent to venue settlement or a bankroll write. |
| Bounded recovery | Transport retries have finite budgets; unresolved failure remains visible | Reconnection and continuity qualification do not automatically restore all per-instrument freshness guarantees. |
| Testing | Regression cases cover state transitions, gaps, overwritten artifacts, interrupted capture, and identity orientation | Mocked and offline cases qualify defined behavior; they do not demonstrate profitable trading or complete live coverage. |

## Settlement and failure preservation

Research lifecycle coordinates distinguish a game that has ended but still awaits terminal settlement from one with an authoritative settled state. Unknown settlement is retained as pending rather than fabricated. These research semantics do not authorize sportsbook settlement or balance changes.

A failed acquisition must leave enough evidence to explain that failure. The stronger lifecycle store writes raw evidence before producing derived state, so an analytical view can be rebuilt from qualified records rather than becoming the only copy of the observation. Durable ownership and acquisition identity reduce duplicate-work ambiguity across restarts.

The scientific records follow the same principle: missing closes, unavailable same-side horizons, and killed hypotheses remain visible. No successful-outcome-only filtering is introduced for the portfolio.

## Inspectability

The [claim-evidence inventory](../evidence/README.md) publishes sanitized numerical excerpts and their source digests. Those excerpts support checking arithmetic, counts, units, and the figures. Hashes bind artifacts but do not prove external validity or provide access to private data. Engineering concepts are source-inspected claims; the public bundle omits production implementation and operational configuration.
