#Running Notes

## Points Of Confusion on Constitution Parameters

#### 1.
- from "ratified" constitution
```
TFGEN-02 (x - unquantifiable) Any changes to `txFeeFixed` or `txFeeFixed` must consider the implications of reducing the cost of a denial-of-service attack or increasing the maximum transaction fee so that it becomes impossible to construct a transaction.
```
- same items listed twice
- should read `txFeePerByte` and `txFeeFixed`

#### 2.

**Treasury Cut (treasuryCut)**
Part of the rewards mechanism

The treasury cut portion of the monetary expansion is transferred to the treasury before any pool rewards are paid

Can be set in the range 0.0-1.0 (0%-100%)

GUARDRAILS
TC-01 (y) treasuryCut must not be lower than 0.1 (10%)

TC-02 (y) `treasuryCut must not exceed 0.3 (30%)`

TC-03 (y) treasuryCut must not be negative

TC-04 (y) `treasuryCut must not exceed 1.0 (100%)`

TC-05 (~ - no access to change history) treasuryCut must not be changed more than once in any 36 epoch period (approximately 6 months)

- TC-02 and TC-04 appear to conflict or create unecessary redundancy

#### 3.

EIUP-GEN-01 (x - "similar to") The execution prices must be set so ~~tha~~ the

---

## Testing Layouts Below Here

---

## Governance Level Threshold Requirements
- VT-GEN-01 (y) All thresholds must be greater than 50% and less than or equal to 100%
- VT-GEN-02a (y) Economic, network and technical/security parameter thresholds must be in the range 51%-75%
- VT-GEN-03 (y) Governance parameter thresholds must be in the range 75%-90%
- VT-HF-01 (y) Hard fork action thresholds must be in the range 51%-80%
- VT-CON-01 (y) New Constitution or Guardrails Script action thresholds must be in the range 65%-90%
- VT-CC-01 (y) Update Constitutional Committee action thresholds must be in the range 51%-90%
- VT-NC-01 (y) No confidence action thresholds must be in the range 51%-75%

---

## Testing Layouts Below Here

---

## Params

### Copy Pasta From Final Constitution, Test putting in Table
2. Guardrails and Guidelines on Protocol Parameter Update Actions
Below are Guardrails and guidelines for changing updatable protocol parameter settings via the protocol parameter update governance action such that the Cardano Blockchain is never in an unrecoverable state as a result of such changes.

Note that, to avoid ambiguity, this Appendix uses the parameter name that is used in protocol parameter update governance actions rather than any other convention.

GUARDRAILS
PARAM-01 (y) Any protocol parameter that is not explicitly named in this document must not be changed by a Parameter update governance action

PARAM-02a (y) Where a protocol parameter is explicitly listed in this document but no checkable Guardrails are specified, the Guardrails Script must not impose any constraints on changes to the parameter. Checkable Guardrails are shown by a (y)

2.1. Critical Protocol Parameters
The below protocol parameters are critical from a security point of view.

Parameters that are Critical to the Operation of the Blockchain
maximum block body size (maxBlockBodySize)

maximum transaction size (maxTxSize)

maximum block header size (maxBlockHeaderSize)

maximum size of a serialized asset value (maxValueSize)

maximum script execution/memory units in a single block (maxBlockExecutionUnits[steps/memory])

minimum fee coefficient (txFeePerByte)

minimum fee constant (txFeeFixed)

minimum fee per byte for reference scripts (minFeeRefScriptCoinsPerByte)

minimum lovelace deposit per byte of serialized UTxO (utxoCostPerByte)

governance action deposit (govDeposit)

GUARDRAILS
PARAM-03a (y) Critical protocol parameters require an SPO vote in addition to a DRep vote: SPOs must say "yes" with a collective support of more than 50% of all active block production stake. This is enforced by the Guardrails on the stake pool voting threshold.

PARAM-04a (x) At least 3 months should normally pass between the publication of an off-chain proposal to change a critical protocol parameter and the submission of the corresponding on-chain governance action. This Guardrail may be relaxed in the event of a Severity 1 or Severity 2 network issue following careful technical discussion and evaluation.

Parameters that are Critical to the Governance System
delegation key lovelace deposit (stakeAddressDeposit)

pool registration lovelace deposit (stakePoolDeposit)

minimum fixed rewards cut for pools (minPoolCost)

DRep deposit amount (dRepDeposit)

minimal Constitutional Committee size (committeeMinSize)

maximum term length (in epochs) for the Constitutional Committee members (committeeMaxTermLength)

GUARDRAILS
PARAM-05a (y) DReps must vote "yes" with a collective support of more than 50% of all active voting stake. This is enforced by the Guardrails on the DRep voting thresholds.

PARAM-06a (x) At least 3 months should normally pass between the publication of an off-chain proposal to change a parameter that is critical to the governance system and the submission of the corresponding on-chain governance action. This Guardrail may be relaxed in the event of a Severity 1 or Severity 2 network issue following careful technical discussion and evaluation.

2.2. Economic Parameters
The overall goals when managing economic parameters are to:

Enable long-term economic sustainability for the Cardano Blockchain;

Ensure that stake pools are adequately rewarded for maintaining the Cardano Blockchain;

Ensure that ada owners are adequately rewarded for using stake in constructive ways, including when delegating ada for block production; and

Balance economic incentives for different Cardano Blockchain ecosystem stakeholders, including but not limited to Stake Pool Operators, ada owners, DeFi users, infrastructure users, developers (e.g. DApps) and financial intermediaries (e.g. exchanges)

Triggers for Change
Significant changes in the fiat value of ada resulting in potential problems with security, performance, functionality or long-term sustainability

Changes in transaction volumes or types

Community requests or suggestions

Emergency situations that require changes to economic parameters

Counter-indicators
Changes to the economic parameters should not be made in isolation. They need to account for:

External economic factors

Network security concerns

Core Metrics
Fiat value of ada resulting in potential problems with security, performance, functionality or long-term sustainability

Transaction volumes and types

Number and health of stake pools

External economic factors

Changes to Specific Economic Parameters
Transaction fee per byte (txFeePerByte) and fixed transaction fee (txFeeFixed)

Defines the cost for basic transactions in lovelace:

fee(tx) = txFeeFixed + txFeePerByte x nBytes(tx)

GUARDRAILS
TFPB-01 (y) txFeePerByte must not be lower than 30 (0.000030 ada) This protects against low-cost denial of service attacks

TFPB-02 (y) txFeePerByte must not exceed 1,000 (0.001 ada) This ensures that transactions can be paid for

TFPB-03 (y) txFeePerByte must not be negative

TFF-01 (y) txFeeFixed must not be lower than 100,000 (0.1 ada) This protects against low-cost denial of service attacks

TFF-02 (y) txFeeFixed must not exceed 10,000,000 (10 ada) This ensures that transactions can be paid for

TFF-03 (y) txFeeFixed must not be negative

TFGEN-01 (x - "should") To maintain a consistent level of protection agains denial-of-service attacks, txFeeFixed and txFeeFixed should be adjusted whenever Plutus Execution prices are adjusted (executionUnitPrices[steps/memory])

TFGEN-02 (x - unquantifiable) Any changes to txFeeFixed or txFeeFixed must consider the implications of reducing the cost of a denial-of-service attack or increasing the maximum transaction fee so that it becomes impossible to construct a transaction.

UTxO cost per byte (utxoCostPerByte)
Defines the deposit (in lovelace) that is charged for each byte of storage tha is held in a UTxO. This deposit is returned when the UTxO is no longer active.

Sets a minimum threshold on ada that is held within a single UTxO

Provides protection against low-cost denial of service attack on UTxO storage. DoS protection decreases in line with the free node memory (proportional to UTxO growth)

Helps reduce long-term storage costs for node users by providing an incentive to return UTxOs when no longer needed, or to merge UTxOs.

GUARDRAILS
UCPB-01 (y) utxoCostPerByte must not be lower than 3,000 (0.003 ada)

UCPB-02 (y) utxoCostPerByte must not exceed 6,500 (0.0065 ada)

UCPB-03 (y) utxoCostPerByte must not be zero

UCPB-04 (y) utxoCostPerByte must not be negative

UCPB-05a (x - "should") Changes should account for

The acceptable cost of attack

The acceptable time for an attack

The acceptable memory configuration for full node users

The sizes of UTxOs and

The current total node memory usage

Stake address deposit (stakeAddressDeposit)
Ensures that stake addresses are retired when no longer needed

Helps reduce long-term storage costs

Helps limit CPU and memory costs in the ledger

The rationale for the deposit is to incentivize that scarce memory resources are returned when they are no longer required. Reducing the number of active stake addresses also reduces processing and memory costs at the epoch boundary when calculating stake snapshots.

GUARDRAILS
SAD-01 (y) stakeAddressDeposit must not be lower than 1,000,000 (1 ada)

SAD-02 (y) stakeAddressDeposit must not exceed 5,000,000 (5 ada)

SAD-03 (y) stakeAddressDeposit must not be negative

Stake pool deposit (stakePoolDeposit)
Ensures that stake pools are retired by the stake pool operator when no longer needed by them

Helps reduce long-term storage costs
The rationale for the deposit is to incentivize that scarce memory resources are returned when they are no longer required. Rewards and stake snapshot calculations are also impacted by the number of active stake pools.

GUARDRAILS
SPD-01 (y) stakePoolDeposit must not be lower than 250,000,000 (250 ada)

SPD-02 (y) stakePoolDeposit must not exceed 500,000,000 (500 ada)

SPD-03 (y) stakePoolDeposit must not be negative

Minimum Pool Cost (minPoolCost)
Part of the rewards mechanism

The minimum pool cost is transferred to the pool rewards address before any delegator rewards are paid
GUARDRAILS
MPC-01 (y) minPoolCost must not be negative

MPC-02 (y) minPoolCost must not exceed 500,000,000 (500 ada)

MPC-03 (x - "should") minPoolCost should be set in line with the economic cost for operating a pool

Treasury Cut (treasuryCut)
Part of the rewards mechanism

The treasury cut portion of the monetary expansion is transferred to the treasury before any pool rewards are paid

Can be set in the range 0.0-1.0 (0%-100%)

GUARDRAILS
TC-01 (y) treasuryCut must not be lower than 0.1 (10%)

TC-02 (y) treasuryCut must not exceed 0.3 (30%)

TC-03 (y) treasuryCut must not be negative

TC-04 (y) treasuryCut must not exceed 1.0 (100%)

TC-05 (~ - no access to change history) treasuryCut must not be changed more than once in any 36 epoch period (approximately 6 months)

Monetary Expansion Rate (monetaryExpansion)
Part of the rewards mechanism

The monetary expansion controls the amount of reserves that is used for rewards each epoch
Governs the long-term sustainability of the Cardano Blockchain

The reserves are gradually depleted until no rewards are supplied
GUARDRAILS
ME-01 (y) monetaryExpansion must not exceed 0.005

ME-02 (y) monetaryExpansion must not be lower than 0.001

ME-03 (y) monetaryExpansion must not be negative

ME-04 (x - "should") monetaryExpansion should not be varied by more than +/- 10% in any 73-epoch period (approximately 12 months)

ME-05 (x - "should") monetaryExpansion should not be changed more than once in any 36-epoch period (approximately 6 months)

Plutus Script Execution Prices (executionUnitPrices[priceSteps/priceMemory])
Define the fees for executing Plutus scripts

Gives an economic return for Plutus script execution

Provides security against low-cost DoS attacks

GUARDRAILS
EIUP-PS-01 (y) executionUnitPrices[priceSteps] must not exceed 2,000 / 10,000,000

EIUP-PS-02 (y) executionUnitPrices[priceSteps] must not be lower than 500 / 10,000,000

EIUP-PM-01 (y) executionUnitPrices[priceMemory] must not exceed 2,000 / 10,000

EIUP-PM-02 (y) executionUnitPrices[priceMemory] must not be lower than 400 / 10,000

EIUP-GEN-01 (x - "similar to") The execution prices must be set so tha

the cost of executing a transaction with maximum CPU steps is similar to the cost of a maximum sized non-script transaction and

the cost of executing a transaction with maximum memory units is similar to the cost of a maximum sized non-script transaction

EIUP-GEN-02 (x - "should") The execution prices should be adjusted whenever transaction fees are adjusted (txFeeFixed/txFeePerByte). The goal is to ensure that the processing delay is similar for "full" transactions, regardless of their type.

This helps ensure that the requirements on block diffusion/propagation times are met.
Transaction fee per byte for a reference script (minFeeRefScriptCoinsPerByte)
Defines the cost for using Plutus reference scripts in lovelace

GUARDRAILS
MFRS-01 (y) minFeeRefScriptCoinsPerByte must not exceed 1,000 (0.001 ada)

This ensures that transactions can be paid for
MFRS-02 (y) minFeeRefScriptCoinsPerByte must not be negative

MFRS-03 (x - "should") To maintain a consistent level of protection against denial-of-service attacks, minFeeRefScriptCoinsPerByte should be adjusted whenever Plutus Execution prices are adjusted (executionUnitPrices[steps/memory]) and whenever txFeeFixed is adjusted

MFRS-04 (x - unquantifiable) Any changes to minFeeRefScriptCoinsPerByte must consider the implications of reducing the cost of a denial-of-service attack or increasing the maximum transaction fee

2.3. Network Parameters
The overall goals when managing the Cardano Blockchain network parameters are to:

Match the available Cardano Blockchain Layer 1 network capacity to current or future traffic demands, including payment transactions, layer 1 DApps, sidechain management and governance needs

Balance traffic demands for different user groups, including payment transactions, minters of Fungible/Non-Fungible Tokens, Plutus scripts, DeFi developers, Stake Pool Operators and voting transactions

Triggers for Change
Changes to network parameters may be triggered by:

Measured changes in traffic demands over a 2-epoch period (10 days)

Anticipated changes in traffic demands

Cardano Community requests

Counter-indicators
Changes may need to be reversed and/or should not be enacted in the event of:

Excessive block propagation delays

Stake pools being unable to handle traffic volume

Scripts being unable to complete execution

Core Metrics
All decisions on parameter changes should be informed by:

Block propagation delay profile

Traffic volume (block size over time)

Script volume (size of scripts and execution units)

Script execution cost benchmarks

Block propagation delay/diffusion benchmarks

Detailed benchmarking results are required to confirm the effect of any changes on mainnet performance or behavior prior to enactment. The effects of different transaction mixes must be analyzed, including normal transactions, Plutus scripts, and governance actions.

GUARDRAILS
NETWORK-01 (x - "should") No individual network parameter should change more than once per two epochs

NETWORK-02 (x - "should") Only one network parameter should be changed per epoch unless they are directly correlated, e.g., per-transaction and per-block memory unit limits

Changes to Specific Network Parameters
Block Size (maxBlockBodySize)
The maximum size of a block, in Bytes.

GUARDRAILS
MBBS-01 (y) maxBlockBodySize must not exceed 122,880 Bytes (120KB)

MBBS-02 (y) maxBlockBodySize must not be lower than 24,576 Bytes (24KB)

MBBS-03a (x - "exceptional circumstances") maxBlockBodySize must not be decreased, other than in exceptional circumstances where there are potential problems with security, performance, functionality or long-term sustainability

MBBS-04 (~ - no access to existing parameter values) maxBlockBodySize must be large enough to include at least one transaction (that is, maxBlockBodySize must be at least maxTxSize)

MBBS-05 (x - "should") maxBlockBodySize should be changed by at most 10,240 Bytes (10KB) per epoch (5 days), and preferably by 8,192 Bytes (8KB) or less per epoch

MBBS-06 (x - "should") The block size should not induce an additional Transmission Control Protocol (TCP) round trip. Any increase beyond this must be backed by performance analysis, simulation and benchmarking

MBBS-07 (x - "unquantifiable") The impact of any change to maxBlockBodySize must be confirmed by detailed benchmarking/simulation and not exceed the requirements of the block diffusion/propagation time budgets, as described below. Any increase to maxBlockBodySize must also consider future requirements for Plutus script execution (maxBlockExecutionUnits[steps]) against the total block diffusion target of 3s with 95% block propagation within 5s. The limit on maximum block size may be increased in the future if this is supported by benchmarking and monitoring results

Transaction Size (maxTxSize)
The maximum size of a transaction, in Bytes.

GUARDRAILS
MTS-01 (y) maxTxSize must not exceed 32,768 Bytes (32KB)

MTS-02 (y) maxTxSize must not be negative

MTS-03 (~ - no access to existing parameter values) maxTxSize must not be decreased

MTS-04 (~ - no access to existing parameter values) maxTxSize must not exceed maxBlockBodySize

MTS-05 (x - "should") maxTxSize should not be increased by more than 2,560 Bytes (2.5KB) in any epoch, and preferably should be increased by 2,048 Bytes (2KB) or less per epoch

MTS-06 (x - "should") maxTxSize should not exceed 1/4 of the block size

Memory Unit Limits (maxBlockExecutionUnits[memory], maxTxExecutionUnits[memory])
The limit on the maximum number of memory units that can be used by Plutus scripts, either per-transaction or per-block.

GUARDRAILS
MTEU-M-01 (y) maxTxExecutionUnits[memory] must not exceed 40,000,000 units

MTEU-M-02 (y) maxTxExecutionUnits[memory] must not be negative

MTEU-M-03 (~ - no access to existing parameter values) maxTxExecutionUnits[memory] must not be decreased

MTEU-M-04 (x - "should") maxTxExecutionUnits[memory] should not be increased by more than 2,500,000 units in any epoch

MBEU-M-01 (y) maxBlockExecutionUnits[memory] must not exceed 120,000,000 units

MBEU-M-02 (y) maxBlockExecutionUnits[memory] must not be negative

MBEU-M-03 (x - "should") maxBlockExecutionUnits[memory] should not be changed (increased or decreased) by more than 10,000,000 units in ANY epoch

MBEU-M-04a (x - unquantifiable) The impact of any change to maxBlockExecutionUnits[memory] must be confirmed by detailed benchmarking/simulation and not exceed the requirements of the block diffusion/propagation time budgets, as also impacted by maxBlockExecutionUnits[steps] and maxBlockBodySize. Any increase must also consider previously agreed future requirements for the total block size (maxBlockBodySize) measured against the total block diffusion target of 3s with 95% block propagation within 5s. Future Plutus performance improvements may allow the per-block memory limit to be increased, but must be balanced against the overall diffusion limits as specified in the previous sentence, and future requirements

MEU-M-01 (~ - no access to existing parameter values) maxBlockExecutionUnits[memory] must not be less than maxTxExecutionUnits[memory]

CPU Unit Limits (maxBlockExecutionUnits[steps], maxTxExecutionUnits[steps])
The limit on the maximum number of CPU steps that can be used by Plutus scripts, either per transaction or per-block.

GUARDRAILS
MTEU-S-01 (y) maxTxExecutionUnits[steps] must not exceed 15,000,000,000 (15Bn) units

MTEU-S-02 (y) maxTxExecutionUnits[steps] must not be negative

MTEU-S-03 (~ - no access to existing parameter values) maxTxExecutionUnits[steps] must not be decreased

MTEU-S-04 (x - "should") maxTxExecutionUnits[steps] should not be increased by more than 500,000,000 (500M) units in any epoch (5 days)

MBEU-S-01 (y) maxBlockExecutionUnits[steps] must not exceed 40,000,000,000 (40Bn) units

MBEU-S-02 (y) maxBlockExecutionUnits[steps] must not be negative

MBEU-S-03 (x - "should") maxBlockExecutionUnits[steps] should not be changed (increased or decreased) by more than 2,000,000,000 (2Bn) units in any epoch (5 days)

MBEU-S-04a (x - unquantifiable) The impact of the change to maxBlockExecutionUnits[steps] must be confirmed by detailed benchmarking/simulation and not exceed the requirements of the block diffusion/propagation time budgets, as also impacted by maxBlockExecutionUnits[memory] and maxBlockBodySize. Any increase must also consider previously identified future requirements for the total block size (maxBlockBodySize) measured against the total block diffusion target of 3s with 95% block propagation within 5s. Future Plutus performance improvements may allow the per-block step limit to be increased, but must be balanced against the overall diffusion limits as specified in the previous sentence, and future requirements

MEU-S-01 (~ - no access to existing parameter values) maxBlockExecutionUnits[steps] must not be less than maxTxExecutionUnits[steps]

Block Header Size (maxBlockHeaderSize)
The size of the block header.

GUARDRAILS
MBHS-01 (y) maxBlockHeaderSize must not exceed 5,000 Bytes

MBHS-02 (y) maxBlockHeaderSize must not be negative

MBHS-03 (x - "largest valid header" is subject to change) maxBlockHeaderSize must be large enough for the largest valid header

MBHS-04 (x - "should") maxBlockHeaderSize should only normally be increased if the protocol changes

MBHS-05 (x - "should") maxBlockHeaderSize should be within TCP's initial congestion window (3 or 10 MTUs)

2.4. Technical/Security Parameters
The overall goals when managing the technical/security parameters are:

Ensure the security of the Cardano Blockchain network in terms of decentralization and protection against adversarial actions

Enable changes to the Plutus language

Triggers for Change
Changes in the number of active SPOs

Changes to the Plutus language

Security threats

Cardano Community requests

Counter-indicators
Economic concerns, e.g. when changing the number of stake pools
Core Metrics
Number of stake pools

Level of decentralization

Changes to Specific Technical/Security Parameters
Target Number of Stake Pools (stakePoolTargetNum)
Sets the target number of stake pools

The expected number of stake pools when the network is in the equilibrium state

Primarily a security parameter, ensuring decentralization by stake pool division/replication

Has an economic effect as well as a security effect - economic advice is also required when changing this parameter

Large changes in this parameter will trigger mass redelegation events

GUARDRAILS
SPTN-01 (y) stakePoolTargetNum must not be lower than 250

SPTN-02 (y) stakePoolTargetNum must not exceed 2,000

SPTN-03 (y) stakePoolTargetNum must not be negative

SPTN-04 (y) stakePoolTargetNum must not be zero

Pledge Influence Factor (poolPledgeInfluence)
Enables the pledge protection mechanism

Provides protection against Sybil attack

Higher values reward pools that have more pledge and penalize pools that have less pledge
Has an economic effect as well as technical effect - economic advice is also required

GUARDRAILS
PPI-01 (y) poolPledgeInfluence must not be lower than 0.1

PPI-02 (y) poolPledgeInfluence must not exceed 1.0

PPI-03 (y) poolPledgeInfluence must not be negative

PPI-04 (x - "should") poolPledgeInfluence should not vary by more than +/- 10% in any 18-epoch period (approximately 3 months)

Pool Retirement Window (poolRetireMaxEpoch)
Defines the maximum number of epochs notice that a pool can give when planning to retire

GUARDRAILS
PRME-01 (y) poolRetireMaxEpoch must not be negative

PRME-02 (x - "should") poolRetireMaxEpoch should not be lower than 1

Collateral Percentage (collateralPercentage)
Defines how much collateral must be provided when executing a Plutus script as a percentage of the normal execution cost

Collateral is additional to fee payments

If a script fails to execute, then the collateral is lost

The collateral is never lost if a script executes successfully

Provides security against low-cost attacks by making it more expensive rather than less expensive to execute failed scripts

GUARDRAILS
CP-01 (y) collateralPercentage must not be lower than 100

CP-02 (y) collateralPercentage must not exceed 200

CP-03 (y) collateralPercentage must not be negative

CP-04 (y) collateralPercentage must not be zero

Maximum number of collateral inputs (maxCollateralInputs)
Defines the maximum number of inputs that can be used for collateral when executing a Plutus script

GUARDRAILS
MCI-01 (y) maxCollateralInputs must not be lower than 1

Maximum Value Size (maxValueSize)
The limit on the serialized size of the Value in each output.

GUARDRAILS
MVS-01 (y) maxValueSize must not exceed 12,288 Bytes (12KB)

MVS-02 (y) maxValueSize must not be negative

MVS-03 (~ - no access to existing parameter values) maxValueSize must be less than maxTxSize

MVS-04 (~ - no access to existing parameter values) maxValueSize must not be reduced

MVS-05 (x - "sensible output" is subject to interpretation) maxValueSize must be large enough to allow sensible outputs (e.g. any existing on-chain output or anticipated outputs that could be produced by new ledger rules)

Plutus Cost Models (costModels)
Define the base costs for each Plutus primitive in terms of CPU and memory unit

A different cost model is required for each Plutus version. Each cost model comprises many distinct cost model values. Cost models are defined for each Plutus language version. A new language version may introduce additional cost model values or remove existing cost model values.

GUARDRAILS
PCM-01 (x - unquantifiable) Cost model values must be set by benchmarking on a reference architecture

PCM-02 (x - primitives and language versions aren't introduced in transactions) The cost model must be updated if new primitives are introduced or a new Plutus language version is added

PCM-03a (~ - no access to Plutus cost model parameters) Cost model values should not normally be negative. Negative values must be justified against the underlying cost model for the associated primitives

PCM-04 (~ - no access to Plutus cost model parameters) A cost model must be supplied for each Plutus language version that the protocol supports

2.5. Governance Parameters
The overall goals when managing the governance parameters are to:

Ensure governance stability

Maintain a representative form of governance

Triggers for Change
Changes to governance parameters may be triggered by:

Cardano Community requests

Regulatory requirements

Unexpected or unwanted governance outcomes

Entering a state of no confidence

Counter-indicators
Changes may need to be reversed and/or should not be enacted in the event of:

Unexpected effects on governance

Excessive Layer 1 load due to on-chain voting or excessive numbers of governance actions

Core Metrics
All decisions on parameter changes should be informed by:

Governance participation levels

Governance behaviors and patterns

Regulatory considerations

Confidence in the governance system

The effectiveness of the governance system in managing necessary change

Changes to Specific Governance Parameters
Deposit for Governance Actions (govDeposit)
The deposit that is charged when submitting a governance action.

Helps to limit the number of actions that are submitted
GUARDRAILS
GD-01 (y) govDeposit must not be negative

GD-02 (y) govDeposit must not be lower than 1,000,000 (1 ada)

GD-03a (y) govDeposit must not exceed 10,000,000,000,000 (10 million ada)

GD-04 (x - "should") govDeposit should be adjusted in line with fiat changes

Deposit for DReps (dRepDeposit)
The deposit that is charged when registering a DRep.

Helps to limit the number of active DReps
GUARDRAILS
DRD-01 (y) dRepDeposit must not be negative

DRD-02 (y) dRepDeposit must not be lower than 1,000,000 (1 ada)

DRD-03 (y) dRepDeposit must not exceed 100,000,000,000 (100,000 ada)

DRD-04 (x - "should") dRepDeposit should be adjusted in line with fiat changes

DRep Activity Period (dRepActivity)
The period (as a whole number of epochs) after which a DRep is considered to be inactive for vote calculation purposes, if they do not vote on any proposal.

GUARDRAILS
DRA-01 (y) dRepActivity must not be lower than 13 epochs (2 months)

DRA-02 (y) dRepActivity must not exceed 37 epochs (6 months)

DRA-03 (y) dRepActivity must not be negative

DRA-04 (~ - no access to existing parameter values) dRepActivity must be greater than govActionLifetime

DRA-05 (x - "should") dRepActivity should be calculated in human terms (2 months etc)

DRep and SPO Governance Action Thresholds (dRepVotingThresholds[...],poolVotingThresholds[...])
Thresholds on the active voting stake that is required to ratify a specific type of governance action by either DReps or SPOs.

Ensures legitimacy of the action
The threshold parameters are listed below:

dRepVotingThresholds:

dvtCommitteeNoConfidence

dvtCommitteeNormal

dvtHardForkInitiation

dvtMotionNoConfidence

dvtPPEconomicGroup

dvtPPGovGroup

dvtPPNetworkGroup

dvtPPTechnicalGroup

dvtTreasuryWithdrawal

dvtUpdateToConstitution

poolVotingThresholds:

pvtCommitteeNoConfidence

pvtCommitteeNormal

pvtHardForkInitiation

pvtMotionNoConfidence

pvtPPSecurityGroup

GUARDRAILS
VT-GEN-01 (y) All thresholds must be greater than 50% and less than or equal to 100%

VT-GEN-02a (y) Economic, network and technical/security parameter thresholds must be in the range 51%-75%

VT-GEN-03 (y) Governance parameter thresholds must be in the range 75%-90%

VT-HF-01 (y) Hard fork action thresholds must be in the range 51%-80%

VT-CON-01 (y) New Constitution or Guardrails Script action thresholds must be in the range 65%-90%

VT-CC-01 (y) Update Constitutional Committee action thresholds must be in the range 51%-90%

VT-NC-01 (y) No confidence action thresholds must be in the range 51%-75%

Governance Action Lifetime (govActionLifetime)
The period after which a governance action will expire if it is not enacted - as a whole number of epochs

GUARDRAILS
GAL-01 (y) govActionLifetime must not be lower than 1 epoch (5 days)

GAL-03 (x - "should") govActionLifetime should not be lower than 2 epochs (10 days)

GAL-02 (y) govActionLifetime must not exceed 15 epochs (75 days)

GAL-04 (x - "should") govActionLifetime should be calibrated in human terms (eg 30 days, two weeks), to allow sufficient time for voting etc. to take place

GAL-05 (~ - no access to existing parameter values) govActionLifetime must be less than dRepActivity

Maximum Constitutional Committee Term (committeeMaxTermLength)
The limit on the maximum term length that a committee member may serve

GUARDRAILS
CMTL-01a (y) committeeMaxTermLength must not be zero

CMTL-02a (y) committeeMaxTermLength must not be negative

CMTL-03a (y) committeeMaxTermLength must not be lower than 18 epochs (90 days, or approximately 3 months)

CMTL-04a (y) committeeMaxTermLength must not exceed 293 epochs (approximately 4 years)

CMTL-05a (x - "should") committeeMaxTermLength should not exceed 220 epochs (approximately 3 years)

The minimum size of the Constitutional Committee (committeeMinSize)
The least number of members that can be included in a Constitutional Committee following a governance action to change the Constitutional Committee.

GUARDRAILS
CMS-01 (y) committeeMinSize must not be negative

CMS-02 (y) committeeMinSize must not be lower than 3

CMS-03 (y) committeeMinSize must not exceed 10

2.6. Monitoring and Reversion of Parameter Changes
All network parameter changes must be monitored carefully for no less than 2 epochs (10 days)

Changes must be reverted as soon as possible if block propagation delays exceed 4.5s for more than 5% of blocks over any 6 hour rolling window
All other parameter changes should be monitored

The reversion plan should be implemented if the overall effect on performance, security, functionality or long-term sustainability is unacceptable.
A specific reversion/recovery plan must be produced for each parameter change. This plan must include:

Which parameters need to change and in which ways in order to return to the previous state (or a similar state)

How to recover the network in the event of disastrous failure

This plan should be followed if problems are observed following the parameter change. Note that not all changes can be reverted. Additional care must be taken when making changes to these parameters.

2.7. Non-Updatable Protocol Parameters
Some fundamental protocol parameters cannot be changed by the Protocol Parameter Update governance action. These parameters can only be changed in a new Genesis file as part of a hard fork. It is not necessary to provide specific guardrails on updating these parameters.

3. Guardrails and Guidelines on Treasury Withdrawal Actions
Treasury withdrawal actions specify the destination and amount of a number of withdrawals from the Cardano treasury.

GUARDRAILS
TREASURY-01a (x) A net change limit for the Cardano treasury's balance per period of time must be agreed by the DReps via an on-chain governance action with a threshold of greater than 50% of the active voting stake

TREASURY-02a (x) Withdrawals from the Cardano Blockchain treasury made pursuant to an approved Cardano Blockchain ecosystem budget must not exceed the net change limit for the Cardano Treasury's balance per period of time

TREASURY-03a (x) Withdrawals from the Cardano Blockchain treasury must be denominated in ada

TREASURY-04a (x) Withdrawals from the Cardano Blockchain treasury must not be ratified until there is a Cardano Community approved Cardano Blockchain ecosystem budget then in effect pursuant to a previous on-chain governance action agreed by the DReps with a threshold of greater than 50% of the active voting stake

4. Guardrails and Guidelines on Hard Fork Initiation Actions
The hard fork initiation action requires both a new major and a new minor protocol version to be specified.

As positive integers
As the result of a hard fork, new updatable protocol parameters may be introduced. Guardrails may be defined for these parameters, which will take effect following the hard fork. Existing updatable protocol parameters may also be deprecated by the hard fork, in which case the guardrails become obsolete for all future changes.

GUARDRAILS
HARDFORK-01 (~ - no access to existing parameter values) The major protocol version must be the same as or one greater than the major version that will be enacted immediately prior to this change. If the major protocol version is one greater, then the minor protocol version must be zero

HARDFORK-02a (~ - no access to existing parameter values) Unless the major protocol version is also changed, the minor protocol version must be greater than the minor version that will be enacted immediately prior to this change

HARDFORK-03 (~ - no access to existing parameter values) At least one of the protocol versions (major or minor or both) must change

HARDFORK-04a (x) At least 85% of stake pools by active stake should have upgraded to a Cardano Blockchain node version that is capable of processing the rules associated with the new protocol version

HARDFORK-05 (x) Any new updatable protocol parameters that are introduced with a hard fork must be included in this Appendix and suitable guardrails defined for those parameters

HARDFORK-06 (x) Settings for any new protocol parameters that are introduced with a hard fork must be included in the appropriate Genesis file

HARDFORK-07 (x) Any deprecated protocol parameters must be indicated in this Appendix

HARDFORK-08 (~ - no access to Plutus cost model parameters) New Plutus versions must be supported by a version-specific Plutus cost model that covers each primitive that is available in the new Plutus version

5. Guardrails and Guidelines on Update Constitutional Committee or Threshold Actions
Update Constitutional Committee or Threshold governance actions may change the size, composition or required voting thresholds for the Constitutional Committee.

GUARDRAILS
UPDATE-CC-01a (x) Update Constitutional Committee and/or threshold and/or term governance actions must not be ratified until ada holders have ratified through an on-chain governance action this Constitution

6. Guardrails and Guidelines on New Constitution or Guardrails Script Actions
New constitution or Guardrails Script actions change the hash of the on-chain Constitution and the associated Guardrails Script.

GUARDRAILS
NEW-CONSTITUTION-01a (x) A New Constitution or Guardrails Script governance action must be submitted to define any required guardrails for new parameters that are introduced via a Hard Fork governance action

NEW-CONSTITUTION-02 (x) If specified, the new Guardrails Script must be consistent with this Constitution

7. Guardrails and Guidelines on No Confidence Actions
No confidence actions signal a state of no confidence in the governance system. No guardrails are imposed on No Confidence actions.

GUARDRAILS
None
8. GUARDRAILS AND GUIDELINES ON INFO ACTIONS
Info actions are not enacted on-chain. No guardrails are imposed on Info actions.

GUARDRAILS
None
9. List of Protocol Parameter Groups
The protocol parameters are grouped by type, allowing different thresholds to be set for each group.

The network parameter group consists of:

maximum block body size (maxBlockBodySize)

maximum transaction size (maxTxSize)

maximum block header size (maxBlockHeaderSize)

maximum size of a serialized asset value (maxValueSize)

maximum script execution units in a single transaction (maxTxExecutionUnits[steps])

maximum script execution units in a single block (maxBlockExecutionUnits[steps])

maximum number of collateral inputs (maxCollateralInputs)

The economic parameter group consists of:

minimum fee coefficient (txFeePerByte)

minimum fee constant (txFeeFixed)

minimum fee per byte for reference scripts (minFeeRefScriptCoinsPerByte)

delegation key lovelace deposit (stakeAddressDeposit)

pool registration lovelace deposit (stakePoolDeposit)

monetary expansion (monetaryExpansion)

treasury expansion (treasuryCut)

minimum fixed rewards cut for pools (minPoolCost)

minimum lovelace deposit per byte of serialized UTxO (coinsPerUTxOByte)

prices of Plutus execution units (executionUnitPrices[priceSteps/priceMemory])

The technical/security parameter group consists of:

pool pledge influence (poolPledgeInfluence)

pool retirement maximum epoch (poolRetireMaxEpoch)

desired number of pools (stakePoolTargetNum)

Plutus execution cost models (costModels)

proportion of collateral needed for scripts (collateralPercentage)

The governance parameter group consists of:

governance voting thresholds (dRepVotingThresholds[...], poolVotingThresholds[...])

governance action maximum lifetime in epochs (govActionLifetime)

governance action deposit* (govActionDeposit)

DRep deposit amount (dRepDeposit)

DRep activity period in epochs (dRepActivity)

minimal constitutional committee size (committeeMinSize)

maximum term length (in epochs) for the constitutional committee members (committeeMaxTermLength)
