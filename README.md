# Option-price-cauculator
In this project we cauculate option price using Black-Scholes model and explicit method. We will be elaborating the code for explicit method of option pricing and GUI construction.
## 1 Option Contracts and Put/Call Options
An option contract refers to an agreement between two parties to facilitate a potential transaction on the underlying security at a present price, referred to as the strike price, prior to the expiration date. Purchase of an options contract grants you the right, but not an obligation, to buy or sell an underlying asset at a set price on or before a specified date. 
There are two types of contracts, put and call options. A call option gives the holder the right to buy a stock at strike price and a put option gives the holder the right to sell a stock at strike price.  
## 2 Option Pricing Theory
Option pricing models are used to price options by accounting for multiple variables, for instance, current market price, strike price, volatility, interest rate, and time to expiration. Commonly used option pricing models include Black-Scholes, binomial option pricing, and Monte-Carlo simulation.
Options pricing theory also derives various risk factors or sensitivities based on the inputs, which are known as “Greeks”. In the rapidly changing market, the Greeks provide us with means of determining how sensitive a trade is to price fluctuations, volatility fluctuations, and time. Typical Greeks include:
1.	Delta (Δ) – represents the rate of change between the option’s price and a $1 change in the underlying asset’s price
2.	Theta (Θ) – represents the rate of change between the option’s price and time
3.	Gamma (Γ) – represents the rate of change between an option’s delta and the underlying asset’s price
4.	Vega (V) – represents the rate of change between the option’s value and the underlying asset’s implied volatility
5.	Rho (p) – represents the rate of change between the option’s value and a 1% change in the interest rate
## 3 Black-Scholes Model
The Black-Scholes model, also known as the Black-Scholes-Merton (BSM) model, is a mathematical model for pricing an options contract. In particular, the model estimates the variation over time of financial instruments.
The BSM model makes the following assumptions:
-       The option is European and can only be exercised at expiration
-       No dividends are paid out during the life of the option
-       Markets are efficient
-       There are no transaction costs in buying the option
-       The risk-free rate and volatility of the underlying are known and constant
-       The returns on the underlying asset are log-normally distributed
## 4 Foundation of Finite Difference Methods
In this section, we describe the fundamental ideas of finite difference applied to solve the PDE. This section includes approximation of partial derivatives, general discussion of the grid, and the way of formulating boundary conditions.
4.1 The Grid
Consider the Black-Scholes equation in the last section, we perform a discretization leading to a two-dimensional grid. To set up a grid, firstly, we should determine the value of Smax, which is considered as the underlying price unlikely to be reached. Then we discretize the t and S as following,
t=0,δt,2δt,…,Nδt
S=0,δS,2δS,…,MδS
δt and δS are the mesh sized of the discretization of t and S. Following figure illustrates part of the entire grid in the (S,t)-plane. For each node (iδS,jδt), we use the grid notation fi,j=f(iδS,jδt)
![image](https://user-images.githubusercontent.com/62283777/161902195-2e9ea5a3-f13e-496b-bdd9-e04373695647.png)
Theoretical solution  f∗i,j of Black-Scholes equation is defined on the continuous space. In contrast, the approximation solution  fi,j derived from the discretization of the equation is only defined for the nodes. By controlling the parameters Smax, M, N, discretization error can be reduced such that  fi,j is closer to  f∗i,j.

## 5 Explicit Method
Use backward difference approximation for t and central difference for S, expanding at (iδS,jδt),
![image](https://user-images.githubusercontent.com/62283777/161902401-786b7c11-7dc5-41d6-85d6-bd1eb20636eb.png)

![image](https://user-images.githubusercontent.com/62283777/161902414-19fc8b21-0c52-4043-9fb4-133605bc2466.png)
in matrix form

![image](https://user-images.githubusercontent.com/62283777/161902429-c58c5170-5c7d-4687-8e80-0b40fdc7704e.png)

![image](https://user-images.githubusercontent.com/62283777/161902442-ea56152b-989b-481e-9504-d453baa30d8a.png)

