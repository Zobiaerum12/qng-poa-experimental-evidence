# Graph-State Synchronisation and DAG Reorganisation

## Scenario

A previously stopped validator was restarted and allowed to reconnect to the active validators. The experiment examined how the returning validator synchronised its local graph state and resumed participation in the network.

## Observations

Following peer reconnection, graph-state synchronisation was performed.

In one observed recovery run, the QNG runtime explicitly reported:

`spend=5s`

for the graph-state synchronisation event.

The same event also reported a synchronisation count of 19. The precise internal meaning of this count is not established by the available runtime output, so it is recorded here only as an implementation observation and is not interpreted further.

Following graph-state synchronisation, the runtime reported:

`20 blocks processed within a 12.7-second window`

DAG reorganisation was subsequently recorded, followed by further PoA processing.

## Interpretation

The 5-second value represents the graph-state synchronisation duration explicitly reported by QNG in this experimental run. It should not be interpreted as the total validator recovery time or as a general QNG recovery-time benchmark.

The 20 blocks processed within 12.7 seconds represent catch-up processing by the recovering validator. They should not be interpreted as 20 new blocks being generated within 12.7 seconds.

Together, the observations show a recovery sequence involving peer reconnection, graph-state synchronisation, catch-up block processing, DAG reorganisation, and subsequent PoA processing.

These measurements characterise the observed experimental run and are not presented as statistically validated performance measurements.
