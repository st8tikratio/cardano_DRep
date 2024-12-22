# Constitutional Parameters in Alphabetical Order

---

#### Sources
- [IntersectMBO - Constitution - 05 Dec 2024 - markdown](https://github.com/IntersectMBO/draft-constitution/blob/main/2024-12-05/draft-constitution-converted.md)
- [st8tikratio - con-parameters - markdown](https://github.com/st8tikratio/cardano_DRep/blob/main/docs/con-parameters.md)
#### Other Parameter Links
- [Pr-Chang-2 Parameters]()

---

## Parameters ONLY
```
Symbol and Explanation
  - (y) The Guardrail Script can be used to enforce the Guardrail
  - (x) The Guardrail Script cannot be used to enforce the Guardrail
  - (~ - reason) The Guardrail Script cannot be used to enforce the Guardrail for the reason given, but future ledger changes could enable this.
```

| Param Name            |   Parameter/Guardrail         | Value                                                                                                                                                                                                                                                                           |
| -------------------   |  -----------------------      | ----------------                                                                                                                                                                                                                                                                |
| `collateralPercentage`                          | CP-01 (y)                                       | must not be lower than 100    |
|                                                 | CP-02 (y)                                       | must not exceed 200      |
|                                                 | CP-03 (y)                                       | must not be negative      |
|                                                 | CP-04 (y)                                       | must not be zero        |
| `committeeMaxTermLength`                        | CMTL-01a (y)                                    | must not be zero    |
|                                                 | CMTL-02a (y)                                    | must not be negative      |
|                                                 | CMTL-03a (y)                                    | must not be lower than 18 epochs (90 days, or approximately 3 months)      |
|                                                 | CMTL-04a (y)                                    | must not exceed 293 epochs (approximately 4 years)        |
|                                                 | CMTL-05a (x - "should")                         | should not exceed 220 epochs (approximately 3 years)      |
| `committeeMinSize`                              | CMS-01 (y)                                      | must not be negative        |
|                                                 | CMS-02 (y)                                      | must not be lower than 3    |
|                                                 | CMS-03 (y)                                      | must not exceed 10          |
| `dRepActivity`                                  | DRA-01 (y)                                      | must not be lower than 13 epochs (2 months)      |
|                                                 | DRA-02 (y)                                      | must not exceed 37 epochs (6 months)      |
|                                                 | DRA-03 (y)                                      | must not be negative              |
|                                                 | DRA-04 (~ - no access to existing parameter values) | must be greater than govActionLifetime      |
|                                                 | DRA-05 (x - "should")                           | should be calculated in human terms (2 months etc)      |
| `dRepDeposit`                                   | DRD-01 (y)                                      | must not be negative      |
|                                                 | DRD-02 (y)                                      | must not be lower than 1,000,000 (1 ada)    |
|                                                 | DRD-03 (y)                                      | must not exceed 100,000,000,000 (100,000 ada)      |
|                                                 | DRD-04 (x - "should")                           | should be adjusted in line with fiat changes      |
| `executionUnitPrices - General`                 | EIUP-GEN-01 (x - "similar to")                  | The execution prices must be set so that <br> 1. the cost of executing a transaction with maximum CPU steps is similar to the cost of a maximum sized non-script transaction and <br> 2. the cost of executing a transaction with maximum memory units is similar to the cost of a maximum sized non-script transaction    |
|                                                 | EIUP-GEN-02 (x - "should")                      | The execution prices should be adjusted whenever transaction fees are adjusted (txFeeFixed/txFeePerByte). The goal is to ensure that the processing delay is similar for "full" transactions, regardless of their type. <br>  • This helps ensure that the requirements on block diffusion/propagation times are met.        |
| `executionUnitPrices[priceMemory]`              | EIUP-PM-01 (y)                                  | must not exceed 2,000 / 10,000      |
|                                                 | EIUP-PM-02 (y)                                  | must not be lower than 400 / 10,000    |
| `executionUnitPrices[priceSteps]`               | EIUP-PS-01 (y)                                  | must not exceed 2,000 / 10,000,000    | 
|                                                 | EIUP-PS-02 (y)                                  | must not be lower than 500 / 10,000,000   |
| `govActionLifetime`                             | GAL-01 (y)                                      | must not be lower than 1 epoch (5 days)    |
|                                                 | GAL-03 (x - "should")                           | should not be lower than 2 epochs (10 days)      |
|                                                 | GAL-02 (y)                                      | must not exceed 15 epochs (75 days)      |
|                                                 | GAL-04 (x - "should")                           | should be calibrated in human terms (eg 30 days, two weeks), to allow sufficient time for voting etc. to take place      |
|                                                 | GAL-05 (~ - no access to existing parameter values) | must be less than dRepActivity        |
| `govDeposit`                                    | GD-01 (y)                                       | must not be negative    |
|                                                 | GD-02 (y)                                       | must not be lower than 1,000,000 (1 ada)    |
|                                                 | GD-03a (y)                                      | must not exceed 10,000,000,000,000 (10 million ada)     |
|                                                 | GD-04 (x - "should")                            | should be adjusted in line with fiat changes    |
| `HARDFORK`                                      | HARDFORK-01 (~ - no access to existing parameter values) | The major protocol version must be the same as or one greater than the major version that will be enacted immediately prior to this change. If the major protocol version is one greater, then the minor protocol version must be zero |
|                                                 | HARDFORK-02a (~ - no access to existing parameter values)| Unless the major protocol version is also changed, the minor protocol version must be greater than the minor version that will be enacted immediately prior to this change |
|                                                 | HARDFORK-03 (~ - no access to existing parameter values) | At least one of the protocol versions (major or minor or both) must change      |
|                                                 | HARDFORK-04a (x)                                         | At least 85% of stake pools by active stake should have upgraded to a Cardano Blockchain node version that is capable of processing the rules associated with the new protocol version      |
|                                                 | HARDFORK-05 (x)                                          | Any new updatable protocol parameters that are introduced with a hard fork must be included in this Appendix and suitable guardrails defined for those parameters     |
|                                                 | HARDFORK-06 (x)                                          | Settings for any new protocol parameters that are introduced with a hard fork must be included in the appropriate Genesis file    |
|                                                 | HARDFORK-07 (x)                                          | Any deprecated protocol parameters must be indicated in this Appendix        |
|                                                 | HARDFORK-08 (~ - no access to Plutus cost model parameters) | New Plutus versions must be supported by a version-specific Plutus cost model that covers each primitive that is available in the new Plutus version |
| `maxBlockBodySize`                              | MBBS-01 (y)                                        | must not exceed 122,880 Bytes (120KB)           |
|                                                 | MBBS-02 (y)                                        | must not be lower than 24,576 Bytes (24KB)           |
|                                                 | MBBS-03 (x - "exceptional circumstances")          | must not be decreased, other than in exceptional circumstances where there are potential problems with security, performance, functionality or long-term sustainability                                       |            
|                                                 | MBBS-04 (~ - no access to existing parameter values) | must be large enough to include at least one transaction (that is, maxBlockBodySize must be at least maxTxSize)      |
|                                                 | MBBS-05 (x - "should")                               | should be changed by at most 10,240 Bytes (10KB) per epoch (5 days), and preferably by 8,192 Bytes (8KB) or less per epoch        |
|                                                 | MBBS-06 (x - "should")                               | The block size should not induce an additional Transmission Control Protocol (TCP) round trip. Any increase beyond this must be backed by performance analysis, simulation and benchmarking          |
|                                                 | MBBS-07 (x - "unquantifiable")                       | The impact of any change to maxBlockBodySize must be confirmed by detailed benchmarking/simulation and not exceed the requirements of the block diffusion/propagation time budgets, as described below. Any increase to maxBlockBodySize must also consider future requirements for Plutus script execution (maxBlockExecutionUnits[steps]) against the total block diffusion target of 3s with 95% block propagation within 5s. The limit on maximum block size may be increased in the future if this is supported by benchmarking and monitoring results    |
| `maxBlockExecutionUnits[memory]`                | MBEU-M-01 (y)                                      | must not exceed 120,000,000 units    |
|                                                 | MBEU-M-02 (y)                                      | must not be negative    |
|                                                 | MBEU-M-03 (x - "should")                           | should not be changed (increased or decreased) by more than 10,000,000 units in ANY epoch
|                                                 | MBEU-M-04a (x - unquantifiable)                    | The impact of any change to maxBlockExecutionUnits[memory] must be confirmed by detailed benchmarking/simulation and not exceed the requirements of the block diffusion/propagation time budgets, as also impacted by maxBlockExecutionUnits[steps] and maxBlockBodySize. Any increase must also consider previously agreed future requirements for the total block size (maxBlockBodySize) measured against the total block diffusion target of 3s with 95% block propagation within 5s. Future Plutus performance improvements may allow the per-block memory limit to be increased, but must be balanced against the overall diffusion limits as specified in the previous sentence, and future requirements
| `maxBlockExecutionUnits[steps]`                 | MBEU-S-01 (y)                                      | must not exceed 40,000,000,000 (40Bn) units
|                                                 | MBEU-S-02 (y)                                      | must not be negative
|                                                 | MBEU-S-03 (x - "should")                           | should not be changed (increased or decreased) by more than 2,000,000,000 (2Bn) units in any epoch (5 days)
|                                                 | MBEU-S-04a (x - unquantifiable)                    | The impact of the change to maxBlockExecutionUnits[steps] must be confirmed by detailed benchmarking/simulation and not exceed the requirements of the block diffusion/propagation time budgets, as also impacted by maxBlockExecutionUnits[memory] and maxBlockBodySize. Any increase must also consider previously identified future requirements for the total block size (maxBlockBodySize) measured against the total block diffusion target of 3s with 95% block propagation within 5s. Future Plutus performance improvements may allow the per-block step limit to be increased, but must be balanced against the overall diffusion limits as specified in the previous sentence, and future requirements      |
| `maxBlockHeaderSize`                            | MBHS-01 (y)                                     | must not exceed 5,000 Bytes    |
|                                                 | MBHS-02 (y)                                     | must not be negative    |
|                                                 | MBHS-03 (x - "largest valid header" is subject to change)  | must be large enough for the largest valid header    |
|                                                 | MBHS-04 (x - "should")                                     | should only normally be increased if the protocol changes
|                                                 | MBHS-05 (x - "should")                                     | should be within TCP's initial congestion window (3 or 10 MTUs)
| `maxCollateralInputs`                           | MCI-01 (y)                                      | must not be lower than 1        |
| `maxTxExecutionUnits[memory]`                   | MTEU-M-01 (y)                                     | must not exceed 40,000,000 units    |
|                                                 | MTEU-M-02 (y)                                     | must not be negative    |
|                                                 | MTEU-M-03 (~ - no access to existing parameter values) | must not be decreased    |
|                                                 | MTEU-M-04 (x - "should")                           | should not be increased by more than 2,500,000 units in any epoch    |
| `maxTxExecutionUnits[steps]`                    | MTEU-S-01 (y)                                     | must not exceed 15,000,000,000 (15Bn) units      |
|                                                 | MTEU-S-02 (y)                                     | must not be negative        |
|                                                 | MTEU-S-03 (~ - no access to existing parameter values)  | must not be decreased      |
|                                                 | MTEU-S-04 (x - "should")                           | should not be increased by more than 500,000,000 (500M) units in any epoch (5 days)    |
| `maxTxSize`                                     | MTS-01 (y)                                        | must not exceed 32,768 Bytes (32KB)    |
|                                                 | MTS-02 (y)                                        | must not be negative        |
|                                                 | MTS-03 (~ - no access to existing parameter values) | must not be decreased      |
|                                                 | MTS-04 (~ - no access to existing parameter values) | must not exceed maxBlockBodySize    |
|                                                 | MTS-05 (x - "should")                               | should not be increased by more than 2,560 Bytes (2.5KB) in any epoch, and preferably should be increased by 2,048 Bytes (2KB) or less per epoch    |
|                                                 | MTS-06 (x - "should")                               | should not exceed 1/4 of the block size      |
| `maxValueSize`                                  | MVS-01 (y)                                      | must not exceed 12,288 Bytes (12KB)      |
|                                                 | MVS-02 (y)                                      | must not be negative        |
|                                                 | MVS-03 (~ - no access to existing parameter values) | must be less than maxTxSize    |
|                                                 | MVS-04 (~ - no access to existing parameter values) | must not be reduced        |
|                                                 | MVS-05 (x - "sensible output" is subject to interpretation) | maxValueSize must be large enough to allow sensible outputs (e.g. any existing on-chain output or anticipated outputs that could be produced by new ledger rules)     |
| **`MEU`** ___`not Identified`___                | MEU-M-01 (~ - no access to existing parameter values) | maxBlockExecutionUnits[memory] must not be less than maxTxExecutionUnits[memory]
| **`MEU`** ___`not identified`___                | MEU-S-01 (~ - no access to existing parameter values) | maxBlockExecutionUnits[steps] must not be less than maxTxExecutionUnits[steps]    |
| `minFeeRefScriptCoinsPerByte`                   | MFRS-01 (y)                                       | must not exceed 1,000 (0.001 ada) <br> • This ensures that transactions can be paid for 
|                                                 | MFRS-02 (y)                                       | must not be negative
|                                                 | MFRS-03 (x - "should")                            | To maintain a consistent level of protection against denial-of-service attacks, minFeeRefScriptCoinsPerByte should be adjusted whenever Plutus Execution prices are adjusted (executionUnitPrices[steps/memory]) and whenever txFeeFixed is adjusted         |
|                                                 | MFRS-04 (x - unquantifiable)                      | Any changes to minFeeRefScriptCoinsPerByte must consider the implications of reducing the cost of a denial-of-service attack or increasing the maximum transaction fee      |
| `minPoolCost`                                   | MPC-01 (y)                     | must not exceed 500,000,000 (500 ada)                                    |                       
|                                                 | MPC-02 (y)                     | must not be negative                                                     |                                                                                                                                                                                                                                    
|                                                 | MPC-03 (x - "should")          | should be set in line with the economic cost for operating a pool        |
| `monetaryExpansion`                             | ME-01 (y)                                       | must not exceed 0.005                                                                                           |
|                                                 | ME-02 (y)                                       | must not be lower than 0.001                                                                                    |
|                                                 | ME-03 (y)                                       | must not be negative                                                                                            |
|                                                 | ME-04 (x - "should")                            | should not be varied by more than +/- 10% in any 73-epoch period (approximately 12 months)                      |
|                                                 | ME-05 (x - "should")                            | should not be changed more than once in any 36-epoch period (approximately 6 months)                            |  
| `NETWORK`                                       | NETWORK-01 (x - "should")                         | No individual network parameter should change more than once per two epochs    |
|                                                 | NETWORK-02 (x - "should")                         | Only one network parameter should be changed per epoch unless they are directly correlated, e.g., per-transaction and per-block memory unit limits      |
| `NEW-CONSTITUTION`                              | NEW-CONSTITUTION-01a (x)                        | A New Constitution or Guardrails Script governance action must be submitted to define any required guardrails for new parameters that are introduced via a Hard Fork governance action      |
|                                                 | NEW-CONSTITUTION-02 (x)                         | If specified, the new Guardrails Script must be consistent with this Constitution        |
| `PARAM`                                         | PARAM-01 (y)                  | Any protocol parameter that is not explicitly named in this document must not be changed by a Parameter update governance action                                           |
|                                                 | PARAM-02a (y)                 | Where a protocol parameter is explicitly listed in this document but no checkable Guardrails are specified, the Guardrails Script must not impose any constraints on changes to the parameter. Checkable Guardrails are shown by a (y)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                                                 | PARAM-03a (y)                 | Critical protocol parameters require an SPO vote in addition to a DRep vote: SPOs must say "yes" with a collective support of more than 50% of all active block production stake. This is enforced by the Guardrails on the stake pool voting threshold.    |
|                                                 | PARAM-04a (x)                 | At least 3 months should normally pass between the publication of an off-chain proposal to change a critical protocol parameter and the submission of the corresponding on-chain governance action. This Guardrail may be relaxed in the event of a Severity 1 or Severity 2 network issue following careful technical discussion and evaluation.      |
|                                                 | PARAM-05a (y)                 | DReps must vote "yes" with a collective support of more than 50% of all active voting stake. This is enforced by the Guardrails on the DRep voting thresholds.      |
|                                                 | PARAM-06a (x)                 | At least 3 months should normally pass between the publication of an off-chain proposal to change a parameter that is critical to the governance system and the submission of the corresponding on-chain governance action. This Guardrail may be relaxed in the event of a Severity 1 or Severity 2 network issue following careful technical discussion and evaluation.      |
| `plutusCostModel **OR** costModel`              | PCM-01 (x - unquantifiable)                     | Cost model values must be set by benchmarking on a reference architecture      |
|                                                 | PCM-02 (x - primitives and language versions aren't introduced in transactions) | The cost model must be updated if new primitives are introduced or a new Plutus language version is added    |
|                                                 | PCM-03a (~ - no access to Plutus cost model parameters) | Cost model values should not normally be negative. Negative values must be justified against the underlying cost model for the associated primitives      |
|                                                 | PCM-04 (~ - no access to Plutus cost model parameters) | A cost model must be supplied for each Plutus language version that the protocol supports      |
| `poolPledgeInfluence`                           | PPI-01 (y)                                      | must not be lower than 0.1      |
|                                                 | PPI-02 (y)                                      | must not exceed 1.0      |
|                                                 | PPI-03 (y)                                      | must not be negative      |
|                                                 | PPI-04 (x - "should")                           | should not vary by more than +/- 10% in any 18-epoch period (approximately 3 months)    |
| `poolRetireMaxEpoch`                            | PRME-01 (y)                                      | must not be negative      |
|                                                 | PRME-02 (x - "should")                           | should not be lower than 1      |
| `stakeAddressDeposit`                           | SAD-01 (y)                      | must not be lower than 1,000,000 (1 ada    |
|                                                 | SAD-02 (y)                      | must not exceed 5,000,000 (5 ada)          | 
|                                                 | SAD-03 (y)                      | must not be negative                       |                                                                                                                                                                                                        
| `stakePoolDeposit`                              | SPD-01 (y)                      | must not be lower than 250,000,000 (250 ada)          |
|                                                 | SPD-02 (y)                      | must not exceed 500,000,000 (500 ada)                  |  
|                                                 | SPD-03 (y)                      | must not be negative                                  |
| `stakePoolTargetNum`                            | SPTN-01 (y)                                     | must not be lower than 250        |
|                                                 | SPTN-02 (y)                                     | must not exceed 2,000            |
|                                                 | SPTN-03 (y)                                     | must not be negative        |
|                                                 | SPTN-04 (y)                                     | must not be zero          |
| `TREASURY`                                      | TREASURY-01a (x)                                | A net change limit for the Cardano treasury's balance per period of time must be agreed by the DReps via an on-chain governance action with a threshold of greater than 50% of the active voting stake      |
|                                                 | TREASURY-02a (x)                                | Withdrawals from the Cardano Blockchain treasury made pursuant to an approved Cardano Blockchain ecosystem budget must not exceed the net change limit for the Cardano Treasury's balance per period of time    |
|                                                 | TREASURY-03a (x)                                | Withdrawals from the Cardano Blockchain treasury must be denominated in ada      |
|                                                 | TREASURY-04a (x)                                | Withdrawals from the Cardano Blockchain treasury must not be ratified until there is a Cardano Community approved Cardano Blockchain ecosystem budget then in effect pursuant to a previous on-chain governance action agreed by the DReps with a threshold of greater than 50% of the active voting stake
| `treasuryCut`                                   | TC-01 (y)                              | must not be lower than 0.1 (10%)                                          |                                                                                                                                                                                                                                                         
|                                                 | TC-02 (y)                              | must not exceed 0.3 (30%)                                                 | 
|                                                 | TC-03 (y)                              | must not be negative                                                      | 
|                                                 | TC-04 (y)                              | must not exceed 1.0 (100%)         
|                                                 | TC-05 (~ - no access to change history)| must not be changed more than once in any 36 epoch period (approximately 6 months)                                                                                                                                                                                            
| `txFee - General`                               | TFGEN-01 (x - "should")         | To maintain a consistent level of protection agains denial-of-service attacks, txFeeFixed and txFeeFixed should be adjusted whenever Plutus Execution prices are adjusted (executionUnitPrices[steps/memory])                                                                   |
|                                                 | TFGEN-02 (x - unquantifiable)   | Any changes to txFeeFixed or txFeeFixed must consider the implications of reducing the cost of a denial-of-service attack or increasing the maximum transaction fee so that it becomes impossible to construct a transaction.                                                   |
| `txFeeFixed`                                    | TFF-01 (y)                      | must not be lower than 100,000 (0.1 ada)                                                                                                                                                                                                                                        |
|                                                 | TFF-02 (y)                      | must not exceed 10,000,000 (10 ada)                                                                                                                                                                                                                                             | 
|                                                 | TFF-03 (y)                      | must not be negative                                                                                                                                                                                                                                                            |                                                                                                                                                                                                              
| `txFeePerByte`                                  | TFPB-01 (y)                     | must not be lower than 30 (0.000030 ada)                                                                                                                                                                                                                                        |
|                                                 | TFPB-02 (y)                     | must not exceed 1,000 (0.001 ada)                                                                                                                                                                                                                                               | 
|                                                 | TFPB-03 (y)                     | must not be negative                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                
| `UPDATE`                                        | UPDATE-CC-01a (x)                               | Update Constitutional Committee and/or threshold and/or term governance actions must not be ratified until ada holders have ratified through an on-chain governance action this Constitution
| `utxoCostPerByte`                               | UCPB-01 (y)                     | must not be lower than 3,000 (0.003 ada) |
|                                                 | UCPB-02 (y)                     | must not exceed 6,500 (0.0065 ada) |
|                                                 | UCPB-03 (y)                     | must not be zero                                                                                                                                                                                                          
|                                                 | UCPB-04 (y)                     | must not be negative                                                                                                                                                                                                                                    |     
|                                                 | UCPB-05a (x - "should")         | Changes should account for <br> 1. The acceptable cost of attack <br> 2. The acceptable time for an attack <br> 3. The acceptable memory configuration for full node users <br> 4. The sizes of UTxOs and <br> 5. The current total node memory usage   |                                    
| `Vote_Constitution`                             | VT-CON-01 (y)                                   | New Constitution or Guardrails Script action thresholds must be in the range 65%-90%    |
| `Vote_Constitutional-Committee`                 | VT-CC-01 (y)                                    | Update Constitutional Committee action thresholds must be in the range 51%-90%
| `Vote_General`                                  | VT-GEN-01 (y)                                   | All thresholds must be greater than 50% and less than or equal to 100%      |
|                                                 | VT-GEN-02a (y)                                  | Economic, network and technical/security parameter thresholds must be in the range 51%-75%      |
|                                                 | VT-GEN-03 (y)                                   | Governance parameter thresholds must be in the range 75%-90%      |
| `Vote_Hardfork`                                 | VT-HF-01 (y)                                    | Hard fork action thresholds must be in the range 51%-80%    |
| `Vote_No-Confidence`                            | VT-NC-01 (y)                                    | No confidence action thresholds must be in the range 51%-75%





























































