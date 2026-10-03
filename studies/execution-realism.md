# Execution realism: the side-switch reversal control

## Initial Observation

In the Novig historical discovery corpus, a diagnostic control after an execution-side switch showed positive oriented reversal when future executions from either taker side were used. At the **300-second** horizon, the retained mean effect was **+0.267 percentage points**.

## Why It Looked Attractive

A superficial reading could interpret reversal as a repeatable prediction of future value. An execution tape, however, mixes transactions against different sides of the market. Comparing unlike execution sides can create a movement without establishing a change in a common valuation benchmark.

This control was diagnostic from the outset. It was not an eligible trading hypothesis, a deployed strategy, or a failed personal trading campaign.

## Execution Constraint

The same historical control was evaluated using future executions with the **same taker outcome side**. This asks whether the apparent movement remains when the future measurement holds execution side consistent.

The corpus lacks historical order-book depth and midpoint data. It cannot establish queue position, available spread, executable capacity, or actual fills. Same-side execution alignment is a supported measurement control; a complete cost-and-fill simulation would require additional evidence.

## Revised Result

At **300 seconds**, the same-side mean was **−0.013 pp**, compared with **+0.267 pp** using unrestricted future executions. At **60 and 900 seconds**, the all-execution means were **+0.293 and +0.287 pp**, while same-side means were **−0.001 and +0.002 pp**.

![Apparent reversal and the same-side measurement](../figures/novig-side-control.png)

**Source:** [Novig control aggregates](../evidence/novig-aggregates.json), frozen evaluation S5. **Meaning:** oriented execution-price probability movement, averaged equally across games; pp denotes percentage points. **Caveat:** these are point estimates, not realized returns or actual fills. Missing same-side horizons and observational selection limit causal interpretation. This is the same diagnostic evidence discussed in the [Novig study](novig-microstructure.md), not a separate experiment or additional sample.

The apparent effect largely disappeared under execution-side alignment. The evidence supports rejecting a tradability interpretation of the unrestricted tape statistic; it does not measure the net return of an executable strategy.

## Lesson

Displayed or modeled edge is not automatically tradable edge. Here the strongest supported correction was to the measurement itself: specify the execution side before interpreting price movement. Preserve a control that undermines the attractive story, and avoid inventing fills, costs, or profits from data that cannot identify them.
