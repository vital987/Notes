# Basics of Stock Market

- **Interest:** Return on investment of
  - FD, Debentures, etc.
  - Fixed Interest Value
  - Mandatory
  - Taxable
- **Dividend:** Return on investment of
  - Shares
  - Variable Dividend Value
  - Not Mandatory, decision:company
  - Taxable
- **Capital Gain(CG):** Profit made after selling of investment.
- **Long Term Capital Gain(LTCG):** Profit Gain on Holding shares more than 1 Year.
  - Non Taxable Upto ₹1, 00, 000
- **Short Term Capital Gain:** Profit Gain on Holding shares less than 1 Year.
  - No non-taxable limit.
- **Face Value:** Price @ Promoter buys shares.
- **Premium Value:** Market Value - Face Value.
- **Demat:** Dematerialized Format.
- **Turnover:** Profit(Incl. Tax)+Expenses.
- **Profit Before Tax:** Turnover-Expenses.
- **Profit After Tax:** Profit Before Tax-Tax.
- **Topline Growth:** Turnover.
- **Bottomline Growth:** Profit After Tax.
- **STT:** Security Transaction Tax.
- **Broker:** Through which we trade shares.
- **Accounts:**
  - Savings Account: Normal Bank Acc.
  - Demat Account:To hold shares.
  - Trading Account: To trade shares.
- **Myths Busted:**
  - Risky:
    - Short Term, yes.
    - Long Term, very less compared to short term.
  - Finance Knowledge: Analysis skills & logic is good to go.
  - Lot Of Money: Nope.
- **Market Hours:**
  - _9:00-9:15_: Pre-Opening Market Hours
    - _9:00-9:07_: Order Placing
    - _9:08-9:11_: Order Matching
    - _9:12-9:15_: Stabilization
  - _9:15-3:30_: Market Trading Hours
  - _3:30-4:00_: Post Market Hours
  - _4:00-9:00_: After Market Hours
- **Price of shares:**
  - Previous Close:Price when market closed.
  - Open Price: Price when market opened.
  - Bid Price: Buying Price.
  - Offer Price: Selling Price.
  - Latest Traded Price
- **Volume:** Number of shares traded.
- **LTP:** Latest/Last Traded Price.
- **Lot Size:** Multiplier to which one can buy an equity in single trade.
- **Share Price Openings:**
  - Gap-Up Open: Open Price > Close Price
  - Gap-Down Open: Open Price < Close Price
- **Split:** Reduce in Face Value ∝ Share Price.
- **Bonus:** Free shares with decrease in price.
- **Bonus Dates:**
  - Announcement Date: Bonus news.
  - Ex-Bonus Date: Shares should be held by the user before this date to apply for bonus.
  - Record Date: Bonus shares are offered.
- **Bonus Ratio Example:**
  - 1:2, 1 Bonus share for every 2 shares held.
  - 5:6, 5 Bonus share for every 6 shares held.
- **Investor Categories:**
  - RII:Retail Individual Investor, Investment < ₹2L per Company.
  - HNI: High Networth Individual, Investment > ₹2L per Company.
  - DII: Domestic Institutional Investor.
  - FII/FPI: Foreign Institutional Investor/Foreign Portfolio Investor.
- **Depository:** Convert Physical -> Demat Share, Eg: NSDL, CDSL
- **Depository Participant:** Broker.
- **Clearing House:** Helps to transfer the shares from seller's demat account to buyer's demat account. Eg: NSCCL for NSE, ICCL for BSE
- **Primary Market:**
  - Issuer/Company ----> Investor.
  - Where shares are issued for the first time.
  - Also called as New Issue Market (NIM).
  - Sold through Investment Banks.
  - Shares sold directly by companies.
  - Price is fixed or with a limit interval.
- **[ ! ]** When the shares from company to investor are sold, those shares get listed on stock exchanges and hence the company enters in secondary market.
- **Secondary Market:**
  - Investor <----> Investor.
  - Where shares are traded once issued.
  - Also called After Issue Market (AIM).
  - Sold by brokers through stock exchanges.
  - Shares traded among investors only.
  - Prices variable on demand and supply.
- **Contract Note:** Invoice/Proof of Trade.
- **T(Trade Day)+2 Rule:** Transaction is settled after 2 working days from trade date.
- **Orders:** Instruction to buy/sell shares.
- **Order Types Based on Price:**
  - Limit Order: To auto-buy/sell shares at specific price.
  - Market Order: To buy/sell shares at current market price.
  - Stop-Loss Order: Order to auto-sell shares at specific price to prevent more loss, or auto-buy in case of short selling.
    - Stop-Loss Market Order: Order gets triggered at trigger price, and gets immediately executed after being sent to the exchange similar to a market order at the best available bid/offer.
    - Stop-Loss Limit Order: Order gets triggered at trigger price, but gets executed only if there are bids/offers at the Stop loss price.
  - IOC(Immediate Or Cancel) Order: Buy/sell shares ASA the order is released into the market, failing the order will get cancelled.
  - Good Till Day: Order which gets cancelled on the end of the day if not executed.
  - Good Till Cancel: Manual Order cancellation.
  - After Market Order: Order placed after after the market close, will be executed when the market opens.
- **Orders Based on Quantity:**
  - AON(All Or None): Instruction to fill order completely or cancel it, prevent partial fills.
  - MF(Minimum Fill): Instruction to atleast fill an with the minimum number of trade quantity. Eg: MF order with value 20 on 100 shares, meaning their should be atleast 20 shares in single trade, means maximum 5 trades only.
  - DQ(Disclosed Quantity): Allows to disclose only a part of the actual quantity you want to buy/sell.
- **Slippage:** Price gap between the triggered price and the price change, applies to stop loss order.
- **Short selling:** In this case, we place sell order even when if we don't have shares, and when the price goes down resp. to selling price, we buy the shares, hence we earn the profit, short selling is compulsory intraday, in case of shares.
- **[ ! ]** If investor/trader doesn't square-off his position during short sell, then the shares are auctioned in PMH by the broker, and the loss is beared by the investor/trader but the profit is transferred to IEPF (Investor Education & Protection Fund).
- **Circuit Filters:** Stock Exchanges allowshare price to fall/rise with a certain limit, which is the % of the previous close price. Common circuit filters are, 5%, 10%, 20%.
  - Upper Circuit Filter: When share price hits upper CF limit.
  - Lower Circuit Filter: When share price hits lower CF limit.
  - Exceptions:
    - Companies whose derivatives are listed in F&O.
    - Company's first day of listing in SE.
- **Market Wide Circuit Breaker:** Halt in the all trade events due to sudden market crash/gain depending on the CB limit, market can close for the remaining day in extreme conditions.
  - Trigger Limits & Halt Durations:
    | Trigger | Trigger-Time | Halt-Duration |
    |---------|--------------|---------------|
    | 10% | Before 1:00 | 45+15 Mins |
    | | 1:00 to 2:30 | 15+15 Mins |
    | | After 2:30 | No Halt |
    | 15% | Before 1:00 | 105+15Mins |
    | | 1:00 to 2:30 | 45+15 Mins |
    | | After 2:30 | Market Close |
    | 20% | Any Time | Market Close |
- **Market Capatalization:** Refers to how much a company is worth as determined by the stock market.
  - Formula: Total no. of Shares \* Share Price
  - Market Cap Slabs:
    - Penny Stock: <100 Crores
    - Small Cap: <500 Crores
    - Mid Cap: 500 to 10K Crores
    - Large Cap: >10K Crores
  - Bluechip Stocks: Large Cap Stocks.
  - Block/Bulk Deal: Large no. of shares traded in single shot, disclosure is mandatory.
- **Free Float Market Capitalization:** Free floating shares means the total no. of shares minus the shares held by promotors,
  - Formula: Free Floating Shares \* Share Price
- **Bid-Ask Spread:** Difference between the highest price that a buyer is willing to pay for an asset and the lowest price that a seller is willing to accept.
- **Market Indices:**
  - Market Index: Group of major companies based on their M-Cap from each major sector which represents growth of overall market.
  - Two major market indices:
    - NSE: NIFTY (National Fifty)
      - Base Year:Nov 03 1995
      - Base Value: 1000
      - Rebalance Duration: Once in 6M
      - Rebalance Intimacy: Before 4W
      - Owner: IISL(NSE Sub Company)
      - Total Indices: Nifty+66 Sectoral
      - Nifty F&O Lot Size: 50(Current)
    - BSE: SENSEX (Sensitivity Index)
      - Base Year:1978-79
      - Base Value: 100
      - Rebalance Duration: Once in 6M
      - Rebalance Intimacy: Before 4W
      - Owner: BSE
  - Calculation:
    (M-Cap \* Free Floating Shares)%
- **[ ! ] SEBI Rule:** The promoter can hold max. 75% of the total shares and the public should hold min. 25% of total shares, only if the company gets listed.
- **Pledging of Shares by promoters:** Keeping shares as collateral for loans.
- **[ * ]** The loan is given on the value of market price of the share with a huge margins to prevent the losses to the banks when the share crashes.
- **Types of Offerings:**
  - IPO(Initial Public Offer): Company offering shares from unlisted capital.
  - OFS(Offer For Sale): Company offering offering shares from promotor's capital.
  - FPO(Follow on Public Offer): Company offering shares from new unlisted capital.
- **Book Value:** Networth of the company.
  - Calculation: Assets - External Liabilities
- **Merchant Banker:** This entity plays a major role in creating IPO, right from getting the prospectus filled and approval of SEBI till making the sell and planning for IPO.
- **Book Runner Lead Manager (BRLM):** Entity who builds the book (records the bids placed by the investors), during the book building issue(later explained).
- **Underwriter:** Entity who helps in subscription of of the remaining shares till it's issuing limit i.e. 90% it reached in exchange of commision from the company.
- **DRHP(Draft Red Herring Prospectus):** The document stating all the basic information about the company like financials and business operations.
- **RHP(Red Herring Prospectus):** The document stating advanced information about the company like its share price, no. of shares, etc.
- **Benefits of Primary Market:**
  - Tap Larger Markets through IPO.
  - Better disclosure through prospectus.
- **Minimum bidding amount in IPO:** Close to ₹15, 000
- **Lottery System in IPO/FPO:** When an IPO gets oversubscribed by x%, so lottery system only allows shares to 1/x applicant.
- **[ * ]** The share gets listed for first time on SE at 10:00 AM.
- **Price Band:** An interval price (eg: 10 to 20), of a share when they are bidded in primary market.
- **[ * ]** If the investor invests in IPO shares less than its decided price, he will not get shares, but if a investor invests for greater price than decided price, he will get a refund of remaining money.
- **Types of Issues(Primary Market):**
  - Fixed Price Issue: The shares are released from company at fixed price.
  - Book Building Issue: A price band is offered to investors, major bids from the price will be the fixed price of shares. Exceptions my occur, (Case-II in FOC).
    - Fulfillment of criteria: Companies should fill atleast 90% of their public listed share sellings, else their IPO will be cancelled.
- **Case-I:**
  | Price | No. of Bids |
  |-------|-------------|
  | ₹290 | 08 |
  | ₹295 | 80 |
  | ₹300 | 12 |
  - Observation: In this case the price of the share will be decided at ₹295, cause the majority of bids are placed at ₹295.
- **Case-II:**
  | Price | No. of Bids |
  |-------|-------------|
  | ₹290 | 05 |
  | ₹295 | 45 |
  | ₹300 | 50 |
  - Observation: In this case the price of the share will be decided at ₹295, cause if the share price is decided at ₹300, then the company will not able the meet 90% criteria, so the share price will be fixed at ₹295.
- **Registrar & Transfer Agent(RTA):** Entity who transfers shares from company's demat account to investor's demat account.
- **Banker to the Issue:** Entity who monitors transfers from investors to the company's account during the IPO process.
- **Escrow:** Legal concept in which a financial instrument whereby an asset or escrow money is held by a third party who hold the funds or assets until receiving appropriate instructions or until the fulfillment of predetermined contractual obligations among the twoparties who are involved in actual transaction.
- **Application Supported by Blocked Amounts(ASBA):** A facility created by SEBI, in which the amount doesn't gets debited till the the shares gets alloted to that investor, instead the amount gets freezed so no one can benefit free interest on that money.
- **Types of Dumb Investors:**
  - Pigs: Beginners, Invests blindly if gains profits accidentally, and looses all the money at the end.
  - Sheeps: Invests on the tips of major entities, no self strategy.
  - Ostriches: Only focuses on +ve news.
- **Sites Referred:**
  - [MoneyControl](https://moneycontrol.com)
  - [Chittorgarh](https://chittorgarh.com)
  - [TrendLyne](https://trendlyne.com)
  - [TickerTape](https://tickertape.in)
  - [TradingView](https://in.tradingview.com)
---
