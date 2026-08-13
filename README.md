# QNG PoA Experimental Evidence

This repository contains the experimental material used to support our study of Proof-of-Authority (PoA) behaviour in the QNG/MyAmana network.

The experiments were carried out on a three-validator setup and focused on normal network operation, validator shutdown and recovery, graph synchronisation, DAG reorganisation, and behaviour when fewer validators were available.

The repository includes the experiment setup, screenshots, and original runtime logs so that the observations discussed in the manuscript can be traced back to the experimental evidence.

## Experimental Setup

The experiments used the following environment:

- QNG version: `2.3.1+dev-e58a8d3`
- Network: `MyAmana`
- Chain ID: `81341`
- Consensus: Proof-of-Authority (PoA)
- Authorised validators: `3`
- DAG implementation: `PHANTOM`

More information about the setup is available in the `configuration` folder.

## Experiments

The `experiments` folder contains notes for the main scenarios examined during the study:

- `baseline.md` – normal network operation with the validators active.
- `validator_failure_recovery.md` – behaviour when a validator was stopped and later restarted.
- `synchronisation.md` – graph-state synchronisation, catch-up processing, and DAG reorganisation during recovery.
- `reduced_validator_availability.md` – behaviour when the number of active validators was reduced.

## Screenshots

The `screenshots` folder contains screenshots captured during the experiments. These show examples of the runtime behaviour discussed in the manuscript, including validator shutdown and recovery, synchronisation, DAG reorganisation, and the single-validator condition.

## Raw Logs

The `raw-logs` folder contains the original QNG runtime logs from the three validator instances:

- `signer1.log`
- `signer2.log`
- `signer3.log`

These logs are included so that the observations reported in the study can be checked against the original runtime output.

## Notes on the Reported Measurements

The quantitative values reported in the manuscript come from the observed experimental runs.

For example, one recovery run explicitly reported graph-state synchronisation with `spend=5s`. During catch-up, the recovering validator also reported processing 20 blocks within a 12.7-second window.

The 20 blocks processed in 12.7 seconds represent catch-up processing by the recovering validator and should not be interpreted as 20 new blocks being generated in 12.7 seconds.

During the reduced-validator experiments, runtime-reported single-block processing windows of approximately 19.15–20.74 seconds were also observed. When only one validator remained active, the runtime repeatedly reported `signed recently, must wait for others` at approximately 10-second intervals.

These values describe what was observed in the specific experimental runs. They are not intended to represent general performance guarantees for QNG or PoA networks.

## Purpose of this Repository

The purpose of this repository is to keep the experimental evidence associated with the manuscript in one place and make it easier to trace the reported observations back to the screenshots and original runtime logs.
