# Basic Concepts

## Financial Statement Analysis

- Balance Sheet (资产负债表): Provides a **snapshot** of a company's financial position in a single point.
    - Accounting Equation (会计恒等式): Assets = Liabilities + Equity (资产 = 负债 + 所有者权益)
- Income Statement (利润表): Provides a **vedio tape** of a company's financial position in a specific period
    - Revenue - Expenses = Net Income (收入 - 支出 = 净利润).
- Cash Flow Statement (现金流量表): Focus purely on **actual cach movements** over a specific period.

## Risk and Return

- Risk-Free Rate: Theoratical rate of return that carries no risk. In practice we consider the intruments with extremly low risk, e.g. Goverment Treasury Bills (短期国债)

### Capital Asset Pricing Model (CAPM, 资本资产定价模型)

$$E(R_i) = R_f + \beta_i (E(R_m) - R_f)$$

- $E(R_i)$: Expected return of asset $i$
- $R_f$: Risk-free rate
- $\beta_i$ (Beta): A measure of the investment's systematic risk.
    - $\beta_i = 1$: It moves with market.
    - $\beta_i > 1$: Is is more volatile than the market.
    - $\beta_i < 0$: It moves in the opposite direction of the market.
- $E(R_m)$: Expected return of overall market.  
- $E(R_m) - R_f$: Market risk premium (市场风险溢价)

 

## Market Analysis

### Fundamental Analysis (基本面)

Determine an asset's intrinsic value. Valuation (估值) methods is the core of fundamental analysis.

- Company Level:
    - Financial Statements: Balance Sheet, Income Statement, Cash Flow Statement.
    - Management Team
    - Bussiness Model
- Macroeconomic Level:
    - GDP, interest rate, employment data etc.
    - Impact of government policies
    - Geopolitical Events

### Technical Analysis (技术面)

Study historical market data.

- Moving Averages (MA)
- Relative Strength Index (RSI)
- Moving Average Convergence Divergence (MACD)
- Bollinger Bands

### Efficient-Market Hypothesis (EMH, 有效市场假说)

If a piece of information is useful about an asset's value, investors will immediately act on it and price will adjust util the information is no longer making profits.

- Weak-Form Efficiency: All **past market information** are reflected. Technical analysis cannot make profit.
- Semi-Strong Form Efficiency: All **publicly available information** is reflected. Fundamental analysis and technical analysis cannot make profit.
- Strong-Form Efficiency: **All information** are relfected. Even insider information (内幕消息) cannot make profit.

## Investment Vehicles

- Public Offering Funds (公募基金): An investment fund whose shares are offered and sold to the general public.
- Private Funds (私募基金): It raises capital from a limited number of sophisticated investors.

### Passive Portfolio Management（被动组合管理） 

- Index Tracking: Replicate the performance of a market index. 
  - ETFs (Exchange-Traded Funds)
- Use "Buy and Hold" Strategy.
- Diversified across various securities, reducing the risk.
- Lower costs, Simpler, More stable

### Active Portfolio Management（主动组合管理）

- Stock Picking (选股): Based on fundamental analysis, technical analysis, or other strategies.
- Market Timing (择时): Attempts to predict market highs and lows to determine when to buy and hold.
- Activate Adjustment: Portfolios are frequently adjusted based on market changes.
- Risk Control

## Trading

- Position (头寸、持仓)
- Limit Order (限价单)
- Market Order (市价单)
- Liquidity (流动性)
- Exchange (交易所)
- Match (撮合): Pairs buy orders with sell orders to facilitate a trade when their prices meet.
- Maker (挂单方): Places an **limited order** in that is not immediately matched. They are adding liquidity to the market, so exchanges often charge makers lower fees, or even offer rebates.
- Taker (吃单方): Places an **market order** that is immediately matched. They are removing liquidity from the merket, so exchanges often charge takers higher fees than makers.
- Iceberg Order (冰山单): 为了防止投资者对大宗订单做出反应，将大宗订单分成几个小的部分，当可见部分成交后，系统将自动从隐藏部分补充，直到所有订单完成。
- Slippage (滑点): The difference between the expected price of a trade and the price at which the trade is actually executed.
- Dark Pool (暗池): Trading platform that **do not display order book information publicly**.

## High-Frequency Trading (HFT, 高频交易)

- Direct Market Access (DMA, 直接市场接入): 允许投资者将交易指令发送到交易所的撮合系统，而无需经纪商的人工干预，减少了订单处理的延迟
- Co-location (托管机): 高频中为了减少网络延迟，交易所允许高频交易公司将服务器物理地放在离撮合引擎靠近的位置
- Tick: 在高频交易中，一次tick指的是一次市场价格变动或一笔交易

- Passive Strategies
    - Market Making (做市策略): capture profits from the **bid-ask spread (买卖价差)**
    - Arbitrage Trading (套利交易): Profit from very small price differentials for the same asset
- Aggressive Strategies
    - Order Anticipation (订单预测) or Liquidity detection (流动性检测): submit small orders to detect hidden liquidity, trade ahead of a large order to benefit from subsequent price movements.
    - Momentum Ignition (动量点火): 通过快速大量报撤单，制造虚假交易量或波动，从而触发其他算法的交易或散户的跟风盘，然后迅速反向平仓获利。

## Strategy Evaluation

### Backtesting (回测)

### Breadth of Stretegy (BR, 决策广度)

### Information Coefficient (IC, 信息系数)

Evaluate an financial analyst or model. IC shows how closely the forecasts match actual financial results.

IC can range from -1 to 1:
- IC = 1: Perfect prediction
- IC = 0: Random prediction
- IC = -1: Negative prediction

In practice, even IC = 0.05 ~ 0.1 can be considered good.

There are different ways to calculate IC.

#### Normal IC (Pearson Correlation)

$$
r = \rho_{xy} = \frac{\mathrm{Cov}(x, y)}{\sigma_x \sigma_y}
$$

- $x_i$ is the predicted return of asset $i$
- $y_i$ is the actual return of asset $i$
- $\sigma$ means variance

#### Rank IC (Spearman's Rank Correlation)

Instead of using raw values, rank IC calculate correlation using ranks.

$$
r = \rho_{R(x), R(y)} = \frac{\mathrm{Cov}(R(x), R(y))}{\sigma_{R(x)} \sigma_{R(y)}}
$$

#### Calculate Using SciPy

```python
from scipy.stats import pearsonr, spearmanr

# get predicted_returns and actual_returns
# ...

# --- Normal IC (Pearson Correlation) ---
normal_ic, _ = pearsonr(predicted_returns, actual_returns)

# --- Rank IC (Spearman's Rank Correlation) ---
rank_ic, _ = spearmanr(predicted_returns, actual_returns)
```

### Information Ratio (IR, 信息比率)

### 

### Sharpe Ratio (夏普比率)

### Max Drawdown (MDD, 最大回撤)