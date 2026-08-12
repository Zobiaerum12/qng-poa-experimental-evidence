# Reduced Validator Availability

## Scenario

Validator availability was progressively reduced from the original three-validator configuration. The final condition examined the behaviour of the deployment when only one authorised validator remained active.

## Observations

With two authorised validators active, block processing continued.

When availability was reduced to one active validator, the remaining validator repeatedly reported the Clique signing restriction:

`signed recently, must wait for others`

The message was observed repeatedly at approximately 10-second intervals in the examined runtime logs.

Normal block-processing progression was not observed during the examined single-validator condition.

## Interpretation

The repeated signing-restriction messages indicate that the remaining validator continued to enforce the signing rules of the current Clique-based block-production configuration while no other authorised validator was available to participate in the expected signing rotation.

This result should be interpreted as an observation of the tested three-validator QNG/MyAmana configuration. It does not establish that single-validator operation is inherently impossible for Proof-of-Authority or Authorised BlockDAG systems in general.

The observation therefore identifies an operational boundary of the current implementation and motivates further investigation into whether this behaviour originates from authorised participation itself or from Clique-derived scheduling restrictions retained within the block-production layer.

These observations are implementation-level experimental evidence and are not presented as a formal proof of general liveness or fault tolerance.
