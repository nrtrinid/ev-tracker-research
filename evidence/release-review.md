# MVP delivery and public-release review

Reviewed locally on **2026-10-03**, including the adversarial follow-up below. Publication readiness applies only to the verified standalone repository. Copies nested within the private production checkout are assembly working copies, not publication repositories. Nothing was published externally; the production repository remains private.

## Delivered scope

The six frozen deliverables are the [README](../README.md), [Novig study](../studies/novig-microstructure.md), [Kalshi engineering writeup](../engineering/kalshi-market-data.md), [sportsbook calibration study](../studies/sportsbook-calibration.md), [architecture and screenshots](../architecture/README.md), and [execution-realism case study](../studies/execution-realism.md).

Supporting material is limited to [reliability/provenance](../engineering/reliability-and-provenance.md), [claim-evidence notes](README.md), aggregate evidence, figures, and this review. The [Claims and Limitations section](../README.md#claims-and-limitations) is prominent in the README. No additional studies, representative code, website, production-source clone, or deployment artifacts were added.

```text
ev-tracker-research/
├── README.md
├── architecture/
│   ├── README.md
│   └── system-overview.png
├── studies/
│   ├── sportsbook-calibration.md
│   ├── novig-microstructure.md
│   └── execution-realism.md
├── engineering/
│   ├── kalshi-market-data.md
│   └── reliability-and-provenance.md
├── figures/
│   ├── sportsbook-clv.png
│   └── novig-side-control.png
├── screenshots/
│   ├── research-desktop.png
│   └── research-mobile.png
└── evidence/
    ├── README.md
    ├── sportsbook-aggregates.json
    ├── novig-aggregates.json
    └── release-review.md
```

## Comprehensive review

The initial assembly pass covered accuracy, disclosure boundaries, visible image contents, and reviewer readability, followed by focused correction checks. A later read-only adversarial review identified the publication blockers recorded below; their fixes received narrow post-fix verification in the standalone repository.

**Accuracy:** candidate counts were reconciled against retained aggregate outputs and qualification records before drafting. Public excerpts were compared field by field to those outputs. The internal freeze includes candidate hypotheses and a control; the portfolio distinguishes them. Compressed and decompressed evaluation hashes match qualification; the frozen specification matches after normalizing Windows line endings. Counts, exclusions, units, chronological split, and figure values are consistent. No private raw-data rerun, externally registered protocol, confidence interval for the Novig control, realized ROI, actual strategy fills, or live-trading conclusion is claimed.

**Privacy / leakage:** the selected export contains Markdown, aggregate JSON, and PNG images only. Text was checked for machine paths, private URLs, addresses, credential-shaped values, account identifiers, formulas, selection thresholds, and operational configuration. Images were visually inspected; copied capture metadata was empty. No production code, raw provider records, private source mapping, proprietary feature definitions, or credentials are included. Source digests are artifact identity notes, not endpoints or access instructions.

**Recruiter readability:** the README leads with a short private-source disclosure and defined scale facts, then the architecture and study links. The central negative result is visible without reading implementation detail. Each study separates protocol, result, and limitations. The execution case identifies its shared diagnostic evidence rather than suggesting a second independent experiment.

## Findings and focused corrections

| Classification | Finding | Correction / disposition |
|---|---|---|
| BLOCKING — corrected | The Novig plot legend overlapped a numeric annotation | Moved the legend above the plotting area; checked the corrected rendering |
| BLOCKING — corrected | The README's release-review link had no target while the review was being assembled | Added this review with artifact links and tree; verified local targets and heading anchors |
| BLOCKING — corrected | A screenshot inspection description overstated the review as pixel-by-pixel | Replaced it with visual inspection at readable scale and a separate metadata check |
| NON-BLOCKING — improved | The README could be shorter for a first review | Tightened descriptions while preserving disclosure, source notes, and limitations |
| NON-BLOCKING — retained | Private raw records and selected definitions prevent full independent reproduction | Stated explicitly; public aggregate excerpts support arithmetic, unit, and figure inspection |
| NON-BLOCKING — retained | Existing mobile navigation overlaps part of the long screenshot | Preserved the actual capture and disclosed the overlap in its caption |
| NON-BLOCKING — retained | Capture dates and backend state are not independently established | Captions make no production-state, performance, or test-pass inference |

The initial assembly all-clear did not cover publication Git isolation or the README's opening ambiguity. A subsequent read-only adversarial review identified three publication blockers; their remediation and post-fix verification status are recorded below. The private-source inventory remains outside the public artifacts and must not be included in any release.

## Verification and release boundary

Focused verification compared the public excerpts with their private aggregate sources, reconciled counts and partitions, checked source and screenshot digests, validated local Markdown/image links and heading anchors, checked the public file types and sensitive-text patterns, and inspected the corrected visual. The repository doctor completed with one pre-existing warning in unrelated archived documentation; that archive is outside this folder and was left unchanged.

This was a documentation and artifact task. No application behavior changed, no production test qualification is asserted, and no live capture, credential use, order placement, or deployment was performed. No representative implementation is needed for this MVP: the state-machine explanation, preserved implementation limits, numerical artifacts, and aggregate figures provide technical depth without code disclosure.

External publication requires explicit user authorization and a fresh standalone repository containing only these approved artifacts. A working copy nested within the private production repository must never be used as the publication repository.

## Adversarial follow-up and publication isolation

The adversarial verdict for the original working copy was **PUBLICATION_READY_AFTER_FIXES**, with three blockers. Its original read-only report is retained privately outside the public artifacts; the earlier assembly findings above are preserved.

| Blocker | Required correction | Post-fix status |
|---|---|---|
| B1 — Git isolation | Copy only the approved artifacts outside the private checkout and initialize a new repository without inherited history or remotes | Corrected: standalone Git root and metadata; exactly 16 approved staged files, zero inherited commit objects, no shared object-store alternate, and no remote |
| B2 — Opening wording | Qualify execution as analysis and settlement as sportsbook recordkeeping | Corrected in the opening sentence; later limitations retained |
| B3 — Stale all-clear | Preserve the earlier review context, record the adversarial blockers, and verify the isolated tree before declaring readiness | Corrected: earlier all-clear superseded; post-fix status is scoped to the verified standalone repository |

**Post-fix status: PUBLICATION_READY in the verified standalone repository, subject to explicit owner authorization to publish.** No unresolved publication blocker remains in that verified repository. This status does not make an in-parent working copy safe to publish.

The narrow checks passed: the repository owns its Git root and metadata outside the private checkout; its staged allowlist contains exactly the 16 public artifacts in the tree above; no inherited commits, refs, shared object-store alternates, remote, symlink, extra working-tree file, or unstaged change was found. The initial branch is unborn: no commit has been created. The two edited Markdown files and all other approved artifacts match the assembly copy.

All **48** local links/assets and heading anchors passed. Aggregate/source comparisons and capture digests passed; sensitive-text checks had no findings. All five PNGs decoded successfully. Screenshot metadata remains empty, and the explanatory figures contain only benign rendering metadata. No study, figure, or screenshot content was changed by this remediation.

The review authorizes no publication or push. Before an eventual push, verify the intended public remote, the approved tracked-file set, and the new public-only history again. The original private adversarial report and source inventory remain outside the standalone repository.
