Cardano's staking reward system is governed by the formula:

$$ R_{\text{epoch}} = M \times (\text{monetaryExpansion}) + T $$

where $R_{\text{epoch}}$ is the total rewards distributed per epoch, $M$ represents the remaining ADA reserves, and $T$ is the total transaction fees collected in that epoch. The treasury cut is applied before distribution:

$$ R_{\text{stakers}} = (1 - \text{treasuryCut}) \times R_{\text{epoch}} $$

Under the current 20% tax:

$$ R_{\text{stakers}} = 0.80 \times R_{\text{epoch}} $$

Reducing the tax to 10% results in:

$$ R_{\text{stakers}} = 0.90 \times R_{\text{epoch}} $$

This equates to a 12.5% increase in staking rewards across the network. Assuming a baseline staking APY of 4.0%, the reduction would increase APY to approximately 4.5%.
