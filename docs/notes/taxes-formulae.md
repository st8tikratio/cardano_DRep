Cardano's staking reward system is governed by the formula:

$$ R_{\text{epoch}} = M \times (\text{monetaryExpansion}) + T $$

where $R_{\text{epoch}}$ is the total rewards distributed per epoch, $M$ represents the remaining ADA reserves, and $T$ is the total transaction fees collected in that epoch. The treasury cut is applied before distribution:

$$ R_{\text{stakers}} = (1 - \text{treasuryCut}) \times R_{\text{epoch}} $$

Under the current 20% tax:

$$ R_{\text{stakers}} = 0.80 \times R_{\text{epoch}} $$

Reducing the tax to 10% results in:

$$ R_{\text{stakers}} = 0.90 \times R_{\text{epoch}} $$

This equates to a 12.5% increase in staking rewards across the network. Assuming a baseline staking APY of 4.0%, the reduction would increase APY to approximately 4.5%.

---

At significantly higher ADA valuations, the treasury will remain well-funded even with a lower tax rate. This can be expressed as:

$$ T_{\text{future}} = T_{\text{current}} \times \frac{P_{\text{future}}}{P_{\text{current}}} $$

where $T_{\text{future}}$ represents the future treasury value, $T_{\text{current}}$ is the current treasury balance, and $P_{\text{future}}$ and $P_{\text{current}}$ represent the future and current price of ADA, respectively.

---

At higher ADA prices, the treasury retains substantial purchasing power even with a reduced cut. This can be expressed as:

$$ T_{\text{future}} = T_{\text{current}} \times \frac{P_{\text{future}}}{P_{\text{current}}} + \sum_{i=1}^{n} \alpha \cdot T_0 \cdot (1 + g)^i $$

where $T_{{future}}$ represents the future treasury value, $T_{\text{current}}$ is the current treasury balance, $P_{\text{future}}$ and $P_{\text{current}}$ represent the future and current price of ADA, and the second term accounts for treasury inflows from transaction fees, where $\alpha$ is the proportion allocated to the treasury, $T_0$ is the initial transaction revenue, and $g$ is the growth rate of transaction volume.
