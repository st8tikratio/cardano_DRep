# Cardano Governance Thresholds
[Source]()

## SPOs
```
Parameter: poolVotingThresholds
```

| PARAMETER TITLE                      | CURRENT (22-DEC-2024)   | CONSTITUTION THRESHOLD(S) |
|  :----------                        |  :-------------:         |  :------------:           |
| committeeNormal                       | 0.51                   |                           |
| committeeNoConfidence                 | 0.51                   |                           |
| hardForkInitiation                    | 0.51                   |                           |                    
| motionNoConfidence                    | 0.51                   |                           |
| ppSecurityGroup                       | 0.51                   |                           |

## DRep Voting Thresholds
```
Parameter: drepVotingThresholds
```

| PARAMETER TITLE                   | CURRENT (22-DEC-2024)    | CONSTITUTION THRESHOLD(S) |
| :----------                       |  :-------------:         |  :------------:           |
| motionNoConfidence                | 0.67                     |                           |
| committeeNormal                   | 0.67                     |                           |
| committeeNoConfidence             | 0.60                     |                           |
| updateToConstitution              | 0.75                     |                           |
| hardFordInitiation                | 0.60                     |                           |
| ppNetworkGroup                    | 0.67                     |                           |
| ppEconomicGroup                   | 0.67                     |                           |
| ppTechnicalGroup                  | 0.67                     |                           |
| ppGovGroup                        | 0.75                     |                           |
| treasuryWithdrawal                | 0.60                     |                           |

## Constitution Committee

| PARAMETER TITLE                   | CURRENT (22-DEC-2024)    | CONSTITUTION THRESHOLD(S)                    |
| :----------                       |  :-------------:         |  :------------:                              |
| committeeMinSize                  | 7                        |  3 - 10                                      |
| committeeMaxTermLength (epochs)   | 146                      |  18 - 239 epochs <br> 3 months - 4 years     |

## DReps
```
Notes: The Genesis JSON file uses lovelace while the Constitutiton uses ada for drepDeposit
```
| PARAMETER TITLE                   | CURRENT (22-DEC-2024)    | CONSTITUTION THRESHOLD(S)                                     |
| :----------                       |  :-------------:         |  :------------:                                               |
| drepDeposit (lovelace)            | 500000000                | 1,000,000  - 100,000,000,000 lovelace <br> 1 - 100,000 ada    |
| drepActivity (epochs)             | 20                       | 13 - 37 epochs <br> 2 - 6 months                              |

## Governance Actions
```
Notes: Does govAction (from Constitution) = govActionDeposit (from Genesis JSON)?

If yes, goveActionDeposit threshold is: 1,000,000 (1 ada) - 10,000,000,000,000 (10 million ada)
```
| PARAMETER TITLE                   | CURRENT (22-DEC-2024)    | CONSTITUTION THRESHOLD(S)                               |
| :----------                       |  :-------------:         |  :------------:                                         |
| govActionLifetime (epochs)        | 6                        | 1 - 15 epochs <br> 5 - 75 days                          |
| govActionDeposit (lovelace)       | 100000000000             | see Notes above                                         |

## Plutus V3
```
Notes: Does minFeeRefScriptCoinsPerByte	(from constitution) = minFeeRefScriptCostPerByte (from Genesis JSON)?

If yes, Constitution Threshold is: not negative, not > 0.001 ada (1,000 lovelace) 	
```
| PARAMETER TITLE                         | CURRENT (22-DEC-2024)    | CONSTITUTION THRESHOLD(S)                |
| :----------                             |  :-------------:         |  :------------:                          |
| minFeeRefScriptCostPerByte (lovelace)   | 15                       | see Notes above                          |

---
























