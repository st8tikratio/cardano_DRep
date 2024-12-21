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
- Parameters:
  - [05-Dec-2024 Constitution via IMBO](https://github.com/IntersectMBO/draft-constitution/blob/main/2024-12-05/draft-constitution-converted.md)  
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

---
## 2.2 Economic Parameters

### Transaction Fee Per Byte & Fixed Transaction Fee
```
Parameter #1: txFeePerByte
Parameter #2: txFeeFixed

Defines the cost for basic transactions in lovelace:
  • fee(tx) = txFeeFixed + txFeePerByte x nBytes(tx)
```
| Param Name            |   Parameter/Guardrail           | Value                                                                                                                                                                                                                                                                           |
| -------------------   |  :-----------------------:      | ----------------                                                                                                                                                                                                                                                                |
| txFeePerByte          | TFPB-01 (y)                     | must not be lower than 30 (0.000030 ada)                                                                                                                                                                                                                                        |
|                       | TFPB-02 (y)                     | must not exceed 1,000 (0.001 ada)                                                                                                                                                                                                                                               | 
|                       | TFPB-03 (y)                     | must not be negative                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                
| txFeeFixed            | TFF-01 (y)                      | must not be lower than 100,000 (0.1 ada)                                                                                                                                                                                                                                        |
|                       | TFF-02 (y)                      | must not exceed 10,000,000 (10 ada)                                                                                                                                                                                                                                             | 
|                       | TFF-03 (y)                      | must not be negative                                                                                                                                                                                                                                                            |                                                                                                                                                                                                              
| txFeeGeneral (?)      | TFGEN-01 (x - "should")         | To maintain a consistent level of protection agains denial-of-service attacks, txFeeFixed and txFeeFixed should be adjusted whenever Plutus Execution prices are adjusted (executionUnitPrices[steps/memory])                                                                   |
|                       | TFGEN-02 (x - unquantifiable)   | Any changes to txFeeFixed or txFeeFixed must consider the implications of reducing the cost of a denial-of-service attack or increasing the maximum transaction fee so that it becomes impossible to construct a transaction.                                                   |

### UTxO cost per byte
```
Parameter: utxoCostPerByte

Defines the deposit (in lovelace) that is charged for each byte of storage tha is held in a UTxO. This deposit is returned when the UTxO is no longer active.
  • Sets a minimum threshold on ada that is held within a single UTxO
  • Provides protection against low-cost denial of service attack on UTxO storage. DoS protection decreases in line with the free node memory (proportional to UTxO growth)
  • Helps reduce long-term storage costs for node users by providing an incentive to return UTxOs when no longer needed, or to merge UTxOs.
```
| Param Name            |   Parameter/Guardrail           | Value                                                                                                                                                                                                                                                                           |
| -------------------   |  :-----------------------:      | ----------------                                                                                                                                                                                                                                                                |
| utxoCostPerByte       | UCPB-01 (y)                     | must not be lower than 3,000 (0.003 ada) |
|                       | UCPB-02 (y)                     | must not exceed 6,500 (0.0065 ada) |
|                       | UCPB-03 (y)                     | must not be zero                                                                                                                                                                                                          
|                       | UCPB-04 (y)                     | must not be negative                                                                                                                                                                                                                                    |     
|                       | UCPB-05a (x - "should")         | Changes should account for <br> 1. The acceptable cost of attack <br> 2. The acceptable time for an attack <br> 3. The acceptable memory configuration for full node users <br> 4. The sizes of UTxOs and <br> 5. The current total node memory usage   |                                    

### Stake Address Deposit
```
Parameter: stakeAddressDeposit

Ensures that stake addresses are retired when no longer needed
  • Helps reduce long-term storage costs
  • Helps limit CPU and memory costs in the ledger

The rationale for the deposit is to incentivize that scarce memory resources are returned when they are no longer required.
Reducing the number of active stake addresses also reduces processing and memory costs at the epoch boundary when calculating stake snapshots.
```

| Param Name            |   Parameter/Guardrail           | Value                                                                                                                                                                                                                                                                           |
| -------------------   |  :-----------------------:      | ----------------                                                                                                                                                                                                                                                                |
| stakeAddressDeposit   | SAD-01 (y)                      | must not be lower than 1,000,000 (1 ada    |
|                       | SAD-02 (y)                      | must not exceed 5,000,000 (5 ada)          | 
|                       | SAD-03 (y)                      | must not be negative                       |                                                                                                                                                                                                        

### Stake Pool Deposit
```
Parameter: stakePoolDeposit

Ensures that stake pools are retired by the stake pool operator when no longer needed by them
  • Helps reduce long-term storage costs

The rationale for the deposit is to incentivize that scarce memory resources are returned when they are no longer required.
Rewards and stake snapshot calculations are also impacted by the number of active stake pools.


```
| Param Name            |   Parameter/Guardrail           | Value                                                                                                                                                                                                                                                                           |
| -------------------   |  :-----------------------:      | ----------------                                                                                                                                                                                                                                                                |
| stakePoolDeposit      | SPD-01 (y)                      | must not be lower than 250,000,000 (250 ada)          |
|                       | SPD-02 (y)                      | must not exceed 500,000,000 (500 ada)                  |  
|                       | SPD-03 (y)                      | must not be negative                                  |

### Minimum Pool Cost
```
Parameter: minPoolCost

Part of the rewards mechanism
  • The minimum pool cost is transferred to the pool rewards address before any delegator rewards are paid
```

| Param Name            |   Parameter/Guardrail           | Value                                                                                                                                                                                                                                                                           |
| -------------------   |  :-----------------------:      | ----------------                                                                                                                                                                                                                                                                |
| minPoolCost           | MPC-01 (y)                     | must not exceed 500,000,000 (500 ada)                                    |                       
|                       | MPC-02 (y)                     | must not be negative                                                     |                                                                                                                                                                                                                                    
|                       | MPC-03 (x - "should")          | should be set in line with the economic cost for operating a pool        |

### Treasury Cut
```
Parameter: treasuryCut

Part of the rewards mechanism
  • The treasury cut portion of the monetary expansion is transferred to the treasury before any pool rewards are paid
  • Can be set in the range 0.0-1.0 (0%-100%)
```

| Param Name            |   Parameter/Guardrail                  | Value                                                                     |
| -------------------   |  :-----------------------:               | ----------------                                                          |
| treasuryCut           | TC-01 (y)                              | must not be lower than 0.1 (10%)                                          |                                                                                                                                                                                                                                                         
|                       | TC-02 (y)                              | must not exceed 0.3 (30%)                                                 | 
|                       | TC-03 (y)                              | must not be negative                                                      | 
|                       | TC-04 (y)                              | must not exceed 1.0 (100%)         
|                       | TC-05 (~ - no access to change history)| must not be changed more than once in any 36 epoch period (approximately 6 months)                                                                                                                                                                                            


### Monetary Expansion
```
Parameter: monetaryExpansion

Part of the rewards mechanis
  • The monetary expansion controls the amount of reserves that is used for rewards each epoch

Governs the long-term sustainability of the Cardano Blockchain
  • The reserves are gradually depleted until no rewards are supplied
```

| Param Name                                      | Paramter/Guardrail                              |  Value                                                                                                          |
| -------------------------                       | :--------------------:                            | ----------------                                                                                                |
| monetaryExpansion                               | ME-01 (y)                                       | must not exceed 0.005                                                                                           |
|                                                 | ME-02 (y)                                       | must not be lower than 0.001                                                                                    |
|                                                 | ME-03 (y)                                       | must not be negative                                                                                            |
|                                                 | ME-04 (x - "should")                            | should not be varied by more than +/- 10% in any 73-epoch period (approximately 12 months)                      |
|                                                 | ME-05 (x - "should")                            | should not be changed more than once in any 36-epoch period (approximately 6 months)                            |  




##
##
##
##
##
##








|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
|                  |                  |                    |                    |                              |                        |
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

