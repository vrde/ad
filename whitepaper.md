# Onchain Ads

Digital assets thrive on speculation. While our previous experiments with
Harberger taxes and partial common ownership showed promise, they missed a
crucial element: enabling price discovery through "scalpers." Without premiums
exchanging hands between buyers and sellers, the market lacked the speculative
layer that drives early adoption.

Oh et al. [1] demonstrate that scalpers play an essential role in bootstrapping
demand for digital assets. They act as market makers, providing liquidity and
price discovery. This insight led us to redesign our onchain ad mechanism to
explicitly encourage early speculation.

## Harberger tax pricing

Pricing the ad with Harberger taxes has the benefit of the tax burden
increasing with its rising demand. Unlimited private property rights where the
owner doesn't have to pay demand-based recurring fees leads to inefficient
allocation and gives the owner monopoly power. 

The Harberger tax mechanism follows a linear decay function:

$$
p(t) = c \cdot (1 - \frac{t - t_0}{T})
$$

where:
- $p(t)$ is the price at time $t$
- $c$ is the collateral in ETH
- $t_0$ is the time of the last purchase
- $T$ is the period over which the collateral is fully taxed, e.g., 30 days in
  seconds (2,592,000)

The figure below shows the linear price depreciation, dutch auction style.

![Fig 1](https://github.com/user-attachments/assets/353a64a7-406c-4197-bfcb-ca7a7a4c4315)

As the tax period $T$ remains constant, and since the $(1 - \frac{t - t_0}{T})$
part will trend to zero throughout the tax period, the price depreciation of
the property in absolute terms is determined by the size of the collateral $c$.



## References 

1. Oh, Sebeom and Rosen, Samuel and Zhang, Anthony Lee, Digital Veblen Goods
   (December 5, 2023). Available at SSRN: https://ssrn.com/abstract=4042901 or
   http://dx.doi.org/10.2139/ssrn.4042901

## Resources

1. Price to Demand chart: https://excalidraw.com/#json=QsVYulxHf1dXQDJyG26o9,8xmC9Ba_owwJXk_CpX2ypg
2. p(t) on Desmos: https://www.desmos.com/calculator/dpev9ha8vf