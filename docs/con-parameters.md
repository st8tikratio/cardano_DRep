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
| txFee - General       | TFGEN-01 (x - "should")         | To maintain a consistent level of protection agains denial-of-service attacks, txFeeFixed and txFeeFixed should be adjusted whenever Plutus Execution prices are adjusted (executionUnitPrices[steps/memory])                                                                   |
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

| Param Name                                      | Parameter/Guardrail                              |  Value                                                                                                          |
| -------------------------                       | :--------------------:                            | ----------------                                                                                                |
| monetaryExpansion                               | ME-01 (y)                                       | must not exceed 0.005                                                                                           |
|                                                 | ME-02 (y)                                       | must not be lower than 0.001                                                                                    |
|                                                 | ME-03 (y)                                       | must not be negative                                                                                            |
|                                                 | ME-04 (x - "should")                            | should not be varied by more than +/- 10% in any 73-epoch period (approximately 12 months)                      |
|                                                 | ME-05 (x - "should")                            | should not be changed more than once in any 36-epoch period (approximately 6 months)                            |  

### Plutus Script Execution Prices
```
Parameter #1: executionUnitPrices[priceSteps
Parameter #2: executionUnitPrices[priceMemory]

• Define the fees for executing Plutus scripts
• Gives an economic return for Plutus script execution
• Provides security against low-cost DoS attacks
```

| Param Name                                      | Parameter/Guardrail                              |  Value                                                                                                          |
| -------------------------                       | :--------------------:                            | ----------------                                                                                                |
| executionUnitPrices[priceSteps]                 | EIUP-PS-01 (y)                                  | must not exceed 2,000 / 10,000,000    | 
|                                                 | EIUP-PS-02 (y)                                  | must not be lower than 500 / 10,000,000   |
| executionUnitPrices[priceMemory]                | EIUP-PM-01 (y)                                  | must not exceed 2,000 / 10,000      |
|                                                 | EIUP-PM-02 (y)                                  | must not be lower than 400 / 10,000    |
| executionUnitPrices - General                   | EIUP-GEN-01 (x - "similar to")                  | The execution prices must be set so that <br> 1. the cost of executing a transaction with maximum CPU steps is similar to the cost of a maximum sized non-script transaction and <br> 2. the cost of executing a transaction with maximum memory units is similar to the cost of a maximum sized non-script transaction    |
|                                                 | EIUP-GEN-02 (x - "should")                      | The execution prices should be adjusted whenever transaction fees are adjusted (txFeeFixed/txFeePerByte). The goal is to ensure that the processing delay is similar for "full" transactions, regardless of their type. <br>  • This helps ensure that the requirements on block diffusion/propagation times are met.        |

### Transaction Fee Per Byte For A Reference Script
```
Parameter: minFeeRefScriptCoinsPerByte

Defines the cost for using Plutus reference scripts in lovelace
```
| Param Name                                      | Parameter/Guardrail                                |  Value                                                                                                          |
| -------------------------                       | :--------------------:                            | ----------------                                                                                                |
| minFeeRefScriptCoinsPerByte                     | MFRS-01 (y)                                       | must not exceed 1,000 (0.001 ada) <br> • This ensures that transactions can be paid for 
|                                                 | MFRS-02 (y)                                       | must not be negative
|                                                 | MFRS-03 (x - "should")                            | To maintain a consistent level of protection against denial-of-service attacks, minFeeRefScriptCoinsPerByte should be adjusted whenever Plutus Execution prices are adjusted (executionUnitPrices[steps/memory]) and whenever txFeeFixed is adjusted         |
|                                                 | MFRS-04 (x - unquantifiable)                      | Any changes to minFeeRefScriptCoinsPerByte must consider the implications of reducing the cost of a denial-of-service attack or increasing the maximum transaction fee      |

---

## 2.3. Network Parameters
```
The overall goals when managing the Cardano Blockchain network parameters are to:

Match the available Cardano Blockchain Layer 1 network capacity to current or future traffic demands,
including payment transactions, layer 1 DApps, sidechain management and governance needs

Balance traffic demands for different user groups, including payment transactions, minters of
sFungible/Non-Fungible Tokens, Plutus scripts, DeFi developers, Stake Pool Operators and voting transactions
```
### Triggers For Change
```
Changes to network parameters may be triggered by:
  • Measured changes in traffic demands over a 2-epoch period (10 days)
  • Anticipated changes in traffic demands
  • Cardano Community requests
```
### Counter-indicators
```
Changes may need to be reversed and/or should not be enacted in the event of:
  • Excessive block propagation delays
  • Stake pools being unable to handle traffic volume
  • Scripts being unable to complete execution
```
### Core Metrics
```
All decisions on parameter changes should be informed by:
  • Block propagation delay profile
  • Traffic volume (block size over time)
  • Script volume (size of scripts and execution units)
  • Script execution cost benchmarks
  • Block propagation delay/diffusion benchmarks

Detailed benchmarking results are required to confirm the effect of any changes on mainnet performance or
behavior prior to enactment. The effects of different transaction mixes must be analyzed, including normal
transactions, Plutus scripts, and governance actions.
```
### Network
```
Parameter: NETWORK
```

| Param Name                                      | Parameter/Guardrail                                |  Value                                                                                                          |
| -------------------------                       | :--------------------:                            | ----------------                                                                                                |
| NETWORK                                         | NETWORK-01 (x - "should")                         | No individual network parameter should change more than once per two epochs    |
|                                                 | NETWORK-02 (x - "should")                         | Only one network parameter should be changed per epoch unless they are directly correlated, e.g., per-transaction and per-block memory unit limits      |

### Block Size
```
Parameter: maxBlockBodySize

The maximum size of a block, in Bytes.
```

| Param Name                                      | Parameter/Guardrail                                |  Value                                                                                                          |
| -------------------------                       | :--------------------:                            | ----------------                                                                                                |
| maxBlockBodySize                                | MBBS-01 (y)                                        | must not exceed 122,880 Bytes (120KB)           |
|                                                 | MBBS-02 (y)                                        | must not be lower than 24,576 Bytes (24KB)           |
|                                                 | MBBS-03 (x - "exceptional circumstances")          | must not be decreased, other than in exceptional circumstances where there are potential problems with security, performance, functionality or long-term sustainability                                       |            
|                                                 | MBBS-04 (~ - no access to existing parameter values) | must be large enough to include at least one transaction (that is, maxBlockBodySize must be at least maxTxSize)      |
|                                                 | MBBS-05 (x - "should")                               | should be changed by at most 10,240 Bytes (10KB) per epoch (5 days), and preferably by 8,192 Bytes (8KB) or less per epoch        |
|                                                 | MBBS-06 (x - "should")                               | The block size should not induce an additional Transmission Control Protocol (TCP) round trip. Any increase beyond this must be backed by performance analysis, simulation and benchmarking          |
|                                                 | MBBS-07 (x - "unquantifiable")                       | The impact of any change to maxBlockBodySize must be confirmed by detailed benchmarking/simulation and not exceed the requirements of the block diffusion/propagation time budgets, as described below. Any increase to maxBlockBodySize must also consider future requirements for Plutus script execution (maxBlockExecutionUnits[steps]) against the total block diffusion target of 3s with 95% block propagation within 5s. The limit on maximum block size may be increased in the future if this is supported by benchmarking and monitoring results    |

### Transaction Size
```
Parameter: maxTxSize

The maximum size of a transaction, in Bytes.
```

| Param Name                                      | Parameter/Guardrail                                |  Value                                                                                                          |
| -------------------------                       | :--------------------:                            | ----------------                                                                                                |
| maxTxSize                                       | MTS-01 (y)                                        | must not exceed 32,768 Bytes (32KB)    |
|                                                 | MTS-02 (y)                                        | must not be negative        |
|                                                 | MTS-03 (~ - no access to existing parameter values) | must not be decreased      |
|                                                 | MTS-04 (~ - no access to existing parameter values) | must not exceed maxBlockBodySize    |
|                                                 | MTS-05 (x - "should")                               | should not be increased by more than 2,560 Bytes (2.5KB) in any epoch, and preferably should be increased by 2,048 Bytes (2KB) or less per epoch    |
|                                                 | MTS-06 (x - "should")                               | should not exceed 1/4 of the block size      |

### Memory Unit Limits
```
Parameter #1: maxBlockExecutionUnits[memory]
Parameter #2: maxTxExecutionUnits[memory]

The limit on the maximum number of memory units that can be used by Plutus scripts, either per-transaction or per-block.
```

| Param Name                                      | Parameter/Guardrail                                |  Value                                                                                                          |
| -------------------------                       | :--------------------:                            | ----------------                                                                                                |
| maxTxExecutionUnits[memory]                     | MTEU-M-01 (y)                                     | must not exceed 40,000,000 units    |
|                                                 | MTEU-M-02 (y)                                     | must not be negative    |
|                                                 | MTEU-M-03 (~ - no access to existing parameter values) | must not be decreased    |
|                                                 | MTEU-M-04 (x - "should")                           | should not be increased by more than 2,500,000 units in any epoch    |
| maxBlockExecutionUnits[memory]                  | MBEU-M-01 (y)                                      | must not exceed 120,000,000 units    |
|                                                 | MBEU-M-02 (y)                                      | must not be negative    |
|                                                 | MBEU-M-03 (x - "should")                           | should not be changed (increased or decreased) by more than 10,000,000 units in ANY epoch
|                                                 | MBEU-M-04a (x - unquantifiable)                    | The impact of any change to maxBlockExecutionUnits[memory] must be confirmed by detailed benchmarking/simulation and not exceed the requirements of the block diffusion/propagation time budgets, as also impacted by maxBlockExecutionUnits[steps] and maxBlockBodySize. Any increase must also consider previously agreed future requirements for the total block size (maxBlockBodySize) measured against the total block diffusion target of 3s with 95% block propagation within 5s. Future Plutus performance improvements may allow the per-block memory limit to be increased, but must be balanced against the overall diffusion limits as specified in the previous sentence, and future requirements
| **MEU** ___not Identified___         | MEU-M-01 (~ - no access to existing parameter values) | maxBlockExecutionUnits[memory] must not be less than maxTxExecutionUnits[memory]

### CPU Unit Limits
```
Parameter #1:
Parameter #2:

The limit on the maximum number of CPU steps that can be used by Plutus scripts, either per transaction or per-block.
```

| Param Name                                      | Parameter/Guardrail                                |  Value                                                                                                          |
| -------------------------                       | :--------------------:                            | ----------------                                                                                                |
| maxTxExecutionUnits[steps]                      | MTEU-S-01 (y)                                     | must not exceed 15,000,000,000 (15Bn) units      |
|                                                 | MTEU-S-02 (y)                                     | must not be negative        |
|                                                 | MTEU-S-03 (~ - no access to existing parameter values)  | must not be decreased      |
|                                                 | MTEU-S-04 (x - "should")                           | should not be increased by more than 500,000,000 (500M) units in any epoch (5 days)    |
| maxBlockExecutionUnits[steps]                   | MBEU-S-01 (y)                                      | must not exceed 40,000,000,000 (40Bn) units
|                                                 | MBEU-S-02 (y)                                      | must not be negative
|                                                 | MBEU-S-03 (x - "should")                           | should not be changed (increased or decreased) by more than 2,000,000,000 (2Bn) units in any epoch (5 days)
|                                                 | MBEU-S-04a (x - unquantifiable)                    | The impact of the change to maxBlockExecutionUnits[steps] must be confirmed by detailed benchmarking/simulation and not exceed the requirements of the block diffusion/propagation time budgets, as also impacted by maxBlockExecutionUnits[memory] and maxBlockBodySize. Any increase must also consider previously identified future requirements for the total block size (maxBlockBodySize) measured against the total block diffusion target of 3s with 95% block propagation within 5s. Future Plutus performance improvements may allow the per-block step limit to be increased, but must be balanced against the overall diffusion limits as specified in the previous sentence, and future requirements      |
| **MEU** ___NOT IDENTIFIED__                     | MEU-S-01 (~ - no access to existing parameter values) | maxBlockExecutionUnits[steps] must not be less than maxTxExecutionUnits[steps]    |




####
############

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

