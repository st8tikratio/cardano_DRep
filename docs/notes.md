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

#### 4.

---

## Params

### 2.4. Technical/Security Parameters
#### Target Number of Stake Pools (stakePoolTargetNum)
- stakePoolTargetNum must not be lower than 250
- stakePoolTargetNum must not exceed 2,000
#### Pledge Influence Factor (poolPledgeInfluence)
- Higher pledge = higher rewards
- poolPledgeInfluence must not be lower than 0.1
- poolPledgeInfluence must not exceed 1.0
#### Collateral Percentage (collateralPercentage)
- Plutus Script collateral
  - script fails, collateral is lost
- collateralPercentage must not be lower than 100
- collateralPercentage must not exceed 200
#### Maximum number of collateral inputs (maxCollateralInputs)
- maximum number of inputs that can be used for collateral when executing a Plutus script
- maxCollateralInputs must not be lower than 1
#### Maximum Value Size (maxValueSize)
- The limit on the serialized size of the Value in each output.
- maxValueSize must not exceed 12,288 Bytes (12KB)
- ~ maxValueSize must be less than maxTxSize
- ~ maxValueSize must not be reduced
- maxValueSize must be large enough to allow sensible outputs (e.g. any existing on-chain output or anticipated outputs that could be produced by new ledger rules)
#### Plutus Cost Models (costModels)
- Define the base costs for each Plutus primitive in terms of CPU and memory unit
- A different cost model is required for each Plutus version. Each cost model comprises many distinct cost model values. Cost models are defined for each Plutus language version. A new language version may introduce additional cost model values or remove existing cost model values.
- 

