# [TTIO]Individualized Indicator For All: Stock-wise Technical Indicator Optimization with Stock Embedding

![%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled.png](%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled.png)

# Contributions

- Technical Trading Indicator Optimization (TTIO) Model Proposal
- Stock Embedding Based on Collective Behaviors of Fund Managers
- Experiments on Real World Stock Data

# Backgrounds

- '**Technical Analysis**' ↔ 'Fundamental Analysis'
    - **Efficient Market Hypothesis**: Every Public Information is reflected in market price
    - Predict trend, momentum and volatility using **Price** and **Quantity**

    ![%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%201.png](%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%201.png)

- **Indicator Based Portfolio Construction**
    - Top *K*  items based on technical indicator

- **Evaluation:** Rank IC

    ![%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%202.png](%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%202.png)

# Stock Embedding

- Obtain latent representation from mutual fund managers' historical behaviors
- Each fund manager has own preferences, thus leading to a portfolio of stocks with similar properties

## Bipartite Graph Construction

![%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%203.png](%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%203.png)

## Random Walk and Skip-gram

From the bipartite graph, employ random walk and use skip-gram to obtain embeddings from generated sequence of stock items. The link between nodes are probability-weighted.

# Technical Indicator Optimization Model

Use simple feed forward network that learns weights.

$g_i$ : embedding, $w_j$: weights to be trained, $R$: return

![%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%204.png](%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%204.png)

![%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%205.png](%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%205.png)

![%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%206.png](%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%206.png)

![%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%207.png](%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%207.png)

## Rotation Learning

![%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%208.png](%5BTTIO%5DIndividualized%20Indicator%20For%20All%20Stock-wise%20%205d8629c8e69f48a2a6608e1ee2f0fc8e/Untitled%208.png)

# Evaluation

**Benchmark**

1. RAW (raw indicator values)
2. Norm (normalize indicator values)
3. NoEmb
4. Complex (feed concatenated indicator_values + embeddings to feedforward network)

**Metric**

1. Correlation (Rank IC)

 2.  Back Test Return