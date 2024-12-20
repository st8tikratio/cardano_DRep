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


| Section                 | Parameter Name                 | Parameter Type                                 | Value#1                                     | Value#2                            | Value#3              |
| -------                 | --------------                 | -------------                                  | -------------                               | ------------------                 | ---------            |
| 2.1 Critical Parameters |                                |                                                |                                             |                                    |                      |
|                         | txFeePerByte                   | TFPB-01 (y) <br> TFPB-02 (y) <br> TFPB-03 (y)  | must not be lower than 30 (0.000030 ada)    | must not exceed 1,000 (0.001 ada)  | must not be negative |            
|                         | txFeeFixed                     | TFF-01 (y) <br> TFF-02 (y) <br> TFF-03 (y)     | must not be lower than 100,000 (0.1 ada)    | must not exceed 10,000,000 (10 ada)| must not be negative |
|                         |                  |                    |                    |
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

