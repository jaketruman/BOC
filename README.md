# Battle of the C

Sharpe Ratio  
  
$S_{a} =  \frac{E[R_a-R_b]}{\sigma_a}$
---
The **expected return of a portfolio** is the weighted average of the expected returns of the individual assets in the portfolio. The formula is:

Expected Return of Portfolio , $(E(R_p)) = w_1 E(R_1) + w_2 E(R_2) + \dots + w_n E(R_n)$]

Where:
- $( E(R_p) $) = the expected return of the portfolio
- $( w_1, w_2, \dots, w_n $) = the weights of each asset in the portfolio
- $( E(R_1), E(R_2), \dots, E(R_n) $) = the expected returns of the individual assets
---
### Expected Return of an Individual Asset (Probability Approach)

The **expected return of an individual asset** is calculated as the weighted average of its possible returns, where each return is weighted by the probability of its occurrence:

$$
E(R_i) = \sum_{j=1}^{n} P_j \times R_j
$$

Where:
- $E(R_i)$ = the expected return of asset $i$
- $P_j$ = the probability of outcome $j$
- $R_j$ = the return of asset $i$ in outcome $j$
- $n$ = the total number of possible outcomes

---

### Expected Return of an Individual Asset (Historical Data)

If you have **historical data** for an asset's returns, you can calculate the expected return as the average of those historical returns:

$$
E(R_i) = \frac{1}{n} \sum_{j=1}^{n} R_j
$$

Where:
- $E(R_i)$ = the expected return of asset $i$
- $R_j$ = the historical return of asset $i$ in period $j$
- $n$ = the number of historical periods


  
----

# RL Model

***Data*** : We have 3,500,000 rows and 85 columns of histirical stock data. I think we can do PCA tp reduce the dimmesnionalty of features and we probably want to understand what the features actually are.  

***State Space*** : Inital thought is to split all the data into the month and year. Then each stock would have the other columns from the data and we train it moving forward through time. We can add "random start" to the model, so it starts at a random month to avoid potentially overfitting.  


***Action Space*** : So there are 3 actions Buy, Sell, or Hold, we probably want to make these discrete actions. So it can only buy and sell in intervals of $1,000,000. Since there are 30,000 different stocks we need to come up with a way to track the stocks currently in the portfolio. So the agent can only hold or sell stocks in its portfolio.  

***Reward Function*** : We want to use the Sharpe Ratio as the reward if it increases then the rewards increase. The only thing is there are 2 different ways to calculate the expected return value probabilites, and we have to find which one is better 
  
