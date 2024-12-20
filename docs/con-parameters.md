# Parameters
###### 19 Dec 2024
###### 🛑 this doc will not be updated beyond the first governance change to thresholds 🛑

---

- Resources:
  - Plutus:
    - [Chris Moreton's Plutus Pioneer Program Notes](https://plutus-pioneer-program.readthedocs.io/en/latest/plutus_pioneer_program.html)
    - [Cardano Docs - Plutus](https://developers.cardano.org/docs/smart-contracts/plutus/#how-to-guides)
    - [Cardano Developer Resources - Smart Contracts](https://docs.cardano.org/developer-resources/smart-contracts/plutus#plutus-developer-resources)
    - [Plutus User Guide - IOHK](https://plutus.cardano.intersectmbo.org/docs/)
    - [Plutus Repo - IntersectMBO](https://github.com/IntersectMBO/plutus#specifications-and-design)
    - **NONE OF THE ABOVE PROVIDE V3 COST-MODELING**

---
## Cardano Governance Parameters


| PARAMETER SECTION                 | PARAMETER TITLE  | CURRENT (19-DEC-2024)      | CONSTITUTION THRESHOLD(S) |
| ----------                        |  :----------:      |  :-------------:         |  :------------:      |
| **SPOs**                       |   ◀️               |    ◀️                    |  ◀️                  |
| ---- `poolVotingThresholds` ----           |                  |                        |                    |
| committeeNormal                   |                  | 0.51                   |                    |
| committeeNoCOnfidence             |                  | 0.51                   |                    |
| hardForkInitiation                |                  | 0.51                   |                    |
| motionNoConfidence                |                  | 0.51                   |                    |
| ppSecurityGroup                   |                  | 0.51                   |                    |
| **DReps**                         |   ◀️               |    ◀️                    |  ◀️                  |
| ---- `drepVotingThresholds` ----            |                  |                        |                    |
| motionNoConfidence                |                  | 0.67                   |                    |
| committeeNormal                   |                  | 0.67                   |                    |
| committeeNoConfidence             |                  | 0.60                   |                    |
| updateToConstitution              |                  | 0.75                   |                    |
| hardFordInitiation                |                  | 0.60                   |                    |
| ppNetworkGroup                    |                  | 0.67                   |                    |
| ppEconomicGroup                   |                  | 0.67                   |                    |
| ppTechnicalGroup                  |                  | 0.67                   |                    |
| ppGovGroup                        |                  | 0.75                   |                    |
| treasuryWithdrawal                |                  | 0.60                   |                    |
| **Constitution Committee**        |   ◀️               |    ◀️                    |  ◀️                  |
| committeeMinSize                  |                  | 7                      |                    |
| committeeMaxTermLength (epochs)   |                  | 146                    |                    |
| drepDeposit (lovelace)            |                  | 500000000              |                    |
| drepActivity (epochs)             |                  | 20                     |                    |
| **Governance Actions**            |                  |                        |                    |
| govActionLifetime (epochs)        |                  | 6                      |                    |
| govActionDeposit (lovelace)       |                  | 100000000000           |                    |
| **Plutus V3**                     |   ◀️               |    ◀️                    |  ◀️                  |
| minFeeRefScriptCostPerByte (lovelace)|               | 15                     |                    |

---

## Constitution Paramters (05-DEC-2024)
- Symbol and Explanation
  - (y) The Guardrail Script can be used to enforce the Guardrail
  - (x) The Guardrail Script cannot be used to enforce the Guardrail
  - (~ - reason) The Guardrail Script cannot be used to enforce the Guardrail for the reason given, but future ledger changes could enable this.


| Section                          | Parameter Name                 | Parameter Type                                 | Value#1                                     |
| -------                          | --------------                 | -------------                                  | -------------                               |
| 2 Guardrails                     | Guardrails                     | PARAM-01 (y)                                   | Any protocol parameter that is not explicitly named in this document must not be changed by a Parameter update governance action                                           |
|                                  | Guardrails                     | PARAM-02a (y)                                  | Where a protocol parameter is explicitly listed in this document but no checkable Guardrails are specified, the Guardrails Script must not impose any constraints on changes to the parameter. Checkable Guardrails are shown by a (y)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 2.1 Critical Protocol Parameters | _maximum block body size_ (`maxBlockBodySize`) <br> _maximum transaction size_ (`maxTxSize`) <br> _maximum block header size_ (`maxBlockHeaderSize`) <br> _maximum size of a serialized asset value_ (`maxValueSize`) <br> _maximum script execution/memory units in a single block_ (`maxBlockExecutionUnits[steps/memory]`) <br> _minimum fee coefficient_ (`txFeePerByte`) <br> _minimum fee constant_ (`txFeeFixed`) <br> _minimum fee per byte for reference scripts_ (`minFeeRefScriptCoinsPerByte`) <br> _minimum lovelace deposit per byte of serialized UTxO_ (`utxoCostPerByte`) <br> _governance action deposit_ (`govDeposit`)                     | PARAM-03a (y)                                  | Critical protocol parameters require an SPO vote in addition to a DRep vote: SPOs must say "yes" with a collective support of more than 50% of all active block production stake. This is enforced by the Guardrails on the stake pool voting threshold.                                                                                           |
|                                  | _maximum block body size_ (`maxBlockBodySize`) <br> _maximum transaction size_ (`maxTxSize`) <br> _maximum block header size_ (`maxBlockHeaderSize`) <br> _maximum size of a serialized asset value_ (`maxValueSize`) <br> _maximum script execution/memory units in a single block_ (`maxBlockExecutionUnits[steps/memory]`) <br> _minimum fee coefficient_ (`txFeePerByte`) <br> _minimum fee constant_ (`txFeeFixed`) <br> _minimum fee per byte for reference scripts_ (`minFeeRefScriptCoinsPerByte`) <br> _minimum lovelace deposit per byte of serialized UTxO_ (`utxoCostPerByte`) <br> _governance action deposit_ (`govDeposit`)                     | PARAM-04a (x)                                  | At least 3 months should normally pass between the publication of an off-chain proposal to change a critical protocol parameter and the submission of the corresponding on-chain governance action. This Guardrail may be relaxed in the event of a Severity 1 or Severity 2 network issue following careful technical discussion and evaluation.  |
|                                  | _delegation key lovelace deposit_ (`stakeAddressDeposit`) <br> _pool registration lovelace deposit_ (`stakePoolDeposit`) <br> _minimum fixed rewards cut for pools_ (`minPoolCost`) <br> _DRep deposit amount_ (`dRepDeposit`) <br> _minimal Constitutional Committee size_ (`committeeMinSize`) <br> _maximum term length_ (in epochs) _for the Constitutional Committee members_ (`committeeMaxTermLength`)                                                            | PARAM-05a (y)                          | DReps must vote "yes" with a collective support of more than 50% of all active voting stake. This is enforced by the Guardrails on the DRep voting thresholds. |
|                                  | _delegation key lovelace deposit_ (`stakeAddressDeposit`) <br> _pool registration lovelace deposit_ (`stakePoolDeposit`) <br> _minimum fixed rewards cut for pools_ (`minPoolCost`) <br> _DRep deposit amount_ (`dRepDeposit`) <br> _minimal Constitutional Committee size_ (`committeeMinSize`) <br> _maximum term length_ (in epochs) _for the Constitutional Committee members_ (`committeeMaxTermLength`)                                                            | PARAM-06a (x)                          | At least 3 months should normally pass between the publication of an off-chain proposal to change a parameter that is critical to the governance system and the submission of the corresponding on-chain governance action. This Guardrail may be relaxed in the event of a Severity 1 or Severity 2 network issue following careful technical discussion and evaluation. |

| Section                                         | Parameter Name                 | Parameter Type                                 | Value#1                                     | Value#2                            | Value#3              |
| ------------------                              | ---------------                | -------------                                  | --------------                              | -------------                      | ----------------     |
| **2.2. Economic Parameters**                        |                                |                                                |                                             |                                    |                      |          
| Changes to Specific Economic Parameters         | txFeePerByte                   | TFPB-01 (y) <br> TFPB-02 (y) <br> TFPB-03 (y)  | must not be lower than 30 (0.000030 ada)                                                                                                                                                                                        | must not exceed 1,000 (0.001 ada)   | must not be negative  |
|                                                 | txFeeFixed                     | TFF-01 (y) <br> TFF-02 (y) <br> TFF-03 (y)     | must not be lower than 100,000 (0.1 ada)                                                                                                                                                                                        | must not exceed 10,000,000 (10 ada) | must not be negative  |
|                                                 |                                | TFGEN-01 (x - "should")                        | To maintain a consistent level of protection agains denial-of-service attacks, txFeeFixed and txFeeFixed should be adjusted whenever Plutus Execution prices are adjusted (executionUnitPrices[steps/memory])                   |                                    |                  |
|                                                 |                                | TFGEN-02 (x - unquantifiable)                  | Any changes to txFeeFixed or txFeeFixed must consider the implications of reducing the cost of a denial-of-service attack or increasing the maximum transaction fee so that it becomes impossible to construct a transaction.   |                                    |                  |
| UTxO cost per byte (utxoCostPerByte)            | utxoCostPerByte                | UCPB-01 (y) <br> UCPB-02 (y) <br> UCPB-03 (y)  | must not be lower than 3,000 (0.003 ada)                                                                                                                                                                                        | must not exceed 6,500 (0.0065 ada) | must not be zero |
|                                                 | utxoCostPerByte (cont)         | UCPB-04 (y)                                    | must not be negative                   |  |     |
|                                                 | utxoCostPerByte (cont)         | UCPB-05a (x - "should")                        | Changes should account for <br> 1. The acceptable cost of attack <br> 2. The acceptable time for an attack <br> 3. The acceptable memory configuration for full node users <br> 4. The sizes of UTxOs and <br> 5. The current total node memory usage |     |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
---

## Plutus V3 Parameteres


|  Param#1         | Param#2          | Param#3            | Param#4            |
|  -----------     | -----------      | -----------        | --------------     |
| 10788           | 420                 | 1                   | 1                   |
| 1000                | 173                 | 0                   | 1                   |
| 1000                | 59957                 | 4                   | 1                   |
| 11183                 |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |





















|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |
|                  |                  |                    |                    |

