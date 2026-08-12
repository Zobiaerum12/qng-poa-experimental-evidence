# Experimental Setup

The experiments were conducted using a controlled three-validator QNG/MyAmana permissioned blockchain deployment.

## Software and Platform

- QNG version: `2.3.1+dev-e58a8d3`
- Operating system: Ubuntu 24.04.4 LTS
- Deployment environment: Single virtual machine
- Number of authorised validators: 3
- Block-production mechanism: Clique-based Proof-of-Authority (PoA)
- Ledger ordering: MeerDAG
- Execution environment: MeerEVM
- Block-production period: 10 seconds
- Epoch length: 100 blocks
- EVM chain ID: 81341

Each validator ran as an independent process and maintained its own validator identity, data directory, network ports, configuration, and local blockchain state.

## Experimental Scenarios

The experiments examined:

1. Baseline operation with three active validators.
2. Validator shutdown and continued operation with two active validators.
3. Validator restart and recovery.
4. Graph-state synchronisation and DAG reorganisation.
5. Reduced validator availability, including the single-validator condition.

## Scope

The deployment was designed as a controlled experimental environment for examining the runtime behaviour of authorised block production combined with DAG-based ordering. It should not be interpreted as a production-scale or geographically distributed deployment.
