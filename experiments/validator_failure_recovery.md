# Validator Failure and Recovery

## Scenario

One of the three authorised validators was intentionally stopped while the remaining two validators continued operating. The stopped validator was later restarted to examine the recovery process.

## Observations

With two validators active, block processing continued.

Representative runtime-reported single-block processing windows were approximately:

- 19.15--20.74 seconds

Following restart, the validator:

1. Re-established peer connectivity.
2. Synchronised its graph state.
3. Performed catch-up block processing.
4. Underwent DAG reorganisation.
5. Returned to PoA processing.

## Interpretation

The experiment shows that block processing continued with two active validators in the tested three-validator deployment.

Following restart, the stopped validator was able to reconnect, synchronise with the current graph state, and subsequently return to PoA processing.

These observations are implementation-level experimental evidence from the tested configuration and should not be interpreted as a formal proof of general liveness or fault tolerance.
