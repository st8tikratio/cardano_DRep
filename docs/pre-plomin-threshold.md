# Cardano Governance Thresholds
[Source]()

## SPOs
```
Parameter: poolVotingThresholds
```

| GENESIS PARAMETER TITLE   | CONSTITUTION PARAMETER    | CURRENT (22-DEC-2024)  | CONSTITUTION THRESHOLD(S) |
|  :----------              | :----------------:        |  :-------------:       |  :------------:           |
| `committeeNormal`         | VT-CC-01 (y)	            | 0.51                   | 0.51 - 0.90               |
| `committeeNoConfidence`   | VT-NC-01 (y)	            | 0.51                   | 0.51 - 0.75               |
| `hardForkInitiation`      | VT-HF-01 (y)              | 0.51                   | 0.51 - 0.80               |                    
| `motionNoConfidence`      | VT-NC-01 (y) `???`        | 0.51                   | 0.51 - 0.75               |
| `ppSecurityGroup`         | VT-GEN-02a (y)	          | 0.51                   | 0.51 - 0.75               |

## DRep Voting Thresholds
```
Parameter: drepVotingThresholds
```

| GENESIS PARAMETER TITLE   | CONSTITUTION PARAMETER    | CURRENT (22-DEC-2024)    | CONSTITUTION THRESHOLD(S) |
|  :----------              | :----------------:        |  :-------------:         |  :------------:           |
| `motionNoConfidence`      | VT-NC-01 (y) `???`	      | 0.67                     | 0.51 - 0.75               |
| `committeeNormal`         | VT-CC-01 (y)	            | 0.51                     | 0.51 - 0.90               |
| `committeeNoConfidence`   | VT-NC-01 (y)	            | 0.51                     | 0.51 - 0.75               |
| `updateToConstitution`    | VT-CON-01 (y)	            | 0.75                     | 0.65 - 0.90               |
| `hardFordInitiation`      | VT-HF-01 (y)              | 0.60                     | 0.51 - 0.80               |
| `ppNetworkGroup`          | VT-GEN-02a (y)	          | 0.67                     | 0.51 - 0.75               |
| `ppEconomicGroup`         | VT-GEN-02a (y)	          | 0.67                     | 0.51 - 0.75               |
| `ppTechnicalGroup`        | VT-GEN-02a (y)	          | 0.67                     | 0.51 - 0.75               |
| `ppGovGroup`              | VT-GEN-03 (y)	            | 0.75                     | 0.75 - 0.90               |
| `treasuryWithdrawal`      | VT-GEN-02a (y)	          | 0.60                     | 0.50 - 0.75               |

## Constitution Committee

| GENESIS PARAMETER TITLE           | CONSTITUTION PARAMETER                                                                             | CURRENT (22-DEC-2024)    | CONSTITUTION THRESHOLD(S)                    |
|  :----------                      | :----------------:                                                                                 |  :-------------:         |  :------------:                              |
| `committeeMinSize`                | CMS-01 (y) <br> CMS-02 (y) <br> CMS-03 		                                                         | 7                        |  3 - 10                                      |
| `committeeMaxTermLength (epochs)` | CMTL-01a (y) <br> CMTL-02a (y) <br> CMTL-03a (y) <br> CMTL-04a (y)	<br> CMTL-05a (x - "should")	 | 146                      |  18 - 239 epochs <br> 3 months - 4 years     |

## DReps
```
Notes: The Genesis JSON file uses lovelace while the Constitutiton uses ada for drepDeposit
```
| GENESIS PARAMETER TITLE           | CONSTITUTION PARAMETER                                                                                                                  | CURRENT (22-DEC-2024)    | CONSTITUTION THRESHOLD(S)                    |
|  :----------                      | :----------------:                                                                                                                      |  :-------------:         |  :------------:                              |
| `drepDeposit` (lovelace)          | DRD-01 (y)	<br> DRD-02 (y)	<br> DRD-03 (y)	<br> DRD-04 (x - "should")                                                                  | 500000000                | 1,000,000  - 100,000,000,000 lovelace <br> 1 - 100,000 ada    |
| `drepActivity` (epochs)           | DRA-01 (y)	<br> DRA-02 (y)	<br> DRA-03 (y) <br> DRA-04 (~ - no access to existing parameter values)	<br> DRA-05 (x - "should")		    | 20                       | 13 - 37 epochs <br> 2 - 6 months                              |

## Governance Actions
```
Notes: Does govAction (from Constitution) = govActionDeposit (from Genesis JSON)?

If yes, goveActionDeposit threshold is: 1,000,000 (1 ada) - 10,000,000,000,000 (10 million ada)
```
| GENESIS PARAMETER TITLE       | CONSTITUTION PARAMETER    | CURRENT (22-DEC-2024)    | CONSTITUTION THRESHOLD(S) |
|  :----------                  | :----------------:        |  :-------------:         |  :------------:           |
| `govActionLifetime` (epochs)  | GAL-01 (y)	<br> GAL-02 (y)	<br> GAL-03 (x - "should") <br> GAL-04 (x - "should") <br> GAL-05 (~ - no access to existing parameter values) | 6                        | 1 - 15 epochs <br> 5 - 75 days                          |
| `govActionDeposit (lovelace)` | GD-01 (y)	<br> GD-02 (y) <br> GD-03a (y)	<br> GD-04 (x - "should")		                                                                     | 100000000000             | see Notes above                                         |

## Plutus V3
```
Notes: Does minFeeRefScriptCoinsPerByte	(from constitution) = minFeeRefScriptCostPerByte (from Genesis JSON)?

If yes, Constitution Threshold is: not negative, not > 0.001 ada (1,000 lovelace) 	
```
| GENESIS PARAMETER TITLE                 | CONSTITUTION PARAMETER                                                                            | CURRENT (22-DEC-2024)    | CONSTITUTION THRESHOLD(S) |
|  :----------                            | :----------------:                                                                                |  :-------------:         |  :------------:           |
| `minFeeRefScriptCostPerByte (lovelace)` | MFRS-01 (y)	<br> MFRS-02 (y)	<br> 	MFRS-03 (x - "should") <br> 	MFRS-04 (x - unquantifiable)    | 15                       | see Notes above                          |

---
























