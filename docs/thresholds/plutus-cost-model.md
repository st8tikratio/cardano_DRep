####
############

---

## Plutus V3 Parameteres


- Resources:
  - Plutus:
    - [Chris Moreton's Plutus Pioneer Program Notes](https://plutus-pioneer-program.readthedocs.io/en/latest/plutus_pioneer_program.html)
    - [Cardano Docs - Plutus](https://developers.cardano.org/docs/smart-contracts/plutus/#how-to-guides)
    - [Cardano Developer Resources - Smart Contracts](https://docs.cardano.org/developer-resources/smart-contracts/plutus#plutus-developer-resources)
    - [Plutus User Guide - IOHK](https://plutus.cardano.intersectmbo.org/docs/)
    - [Plutus Repo - IntersectMBO](https://github.com/IntersectMBO/plutus#specifications-and-design)
    - **NONE OF THE ABOVE PROVIDE V3 COST-MODELING**
    - [Cost Model | Plutus Documentation - Intersect MBO](https://plutus.cardano.intersectmbo.org/docs/delve-deeper/cost-model)
    - [See also notes.md](https://github.com/st8tikratio/cardano_DRep/blob/main/docs/thresholds/notes.md)


---

# WRONG

| #     | Return Value        | Parameter                                   |
| --    | -----------         | -----------                                 |
| 1.    | 10788               | addInteger-cpu-arguments-intercept          | 
| 2.    | 420                 | addInteger-cpu-arguments-slope              |
| 3.    | 1                   | addInteger-memory-arguments-intercept       |
| 4.    | 1                   | addInteger-memory-arguments-slope           |
| 5.    | 1000                | appendByteString-cpu-arguments-intercept	  |
| 6.    | 173                 | appendByteString-cpu-arguments-slope	      |
| 7.    | 0                   | appendByteString-memory-arguments-intercept |	
| 8.    | 1                   | appendByteString-memory-arguments-slope	    |
| 9.    | 1000                | appendString-cpu-arguments-intercept	      |
| 10.   | 59957               | appendString-cpu-arguments-slope	          |
| 11.   | 4                   | appendString-memory-arguments-intercept	    |
| 12.   | 1                   | appendString-memory-arguments-slope	        |
| 13.   | 11183               | bData-cpu-arguments	                        |       
