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
