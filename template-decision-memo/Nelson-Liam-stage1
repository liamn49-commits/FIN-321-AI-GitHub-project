# Solar Equipment Importer – FX Hedging Decision Memo

**Created by:** [Liam Nelson]  
**Updated by:** [Liam Nelson]  
**Date Created:** [3/2/26]  
**Date Updated:** [3/2/26]  
**Version:** [2]  
**LLM Used:** [Copilot]

---

## Executive Summary
A U.S.-based solar equipment importer expects to receive €4.5 million in one year. Because the firm operates in USD, the future EUR/USD exchange rate directly affects the dollar value of this receivable. To eliminate uncertainty, the firm is evaluating hedging strategies, including a one‑year EUR/USD forward contract at 1.0875. Locking in this rate would guarantee $4.89375 million in proceeds, protecting against euro depreciation. This memo outlines the exposure, risks, hedge alternatives, and the analytical roadmap for building a full FX‑hedging model and final recommendation.

---

## Background & Objectives
The firm purchases solar equipment from European suppliers and receives payments in euros. With a large EUR receivable due in one year, the company faces long‑horizon FX volatility driven by interest rate differentials, macroeconomic cycles, and geopolitical events.

**Primary objective:** Secure the USD value of the future EUR inflow.

**Secondary objectives:** Improve forecasting accuracy, reduce earnings volatility, and comply with internal risk‑management policy.

**The exposure is**  
Currency: EUR → USD  
Amount: €4,500,000  
Timing: Cash receipt expected in 12 months  

**Why it’s risky**  
If the euro depreciates, the USD value of the receivable falls.

Examples:  
- Forward rate = 1.0875 → USD proceeds = $4,893,750  
- If spot falls to 1.00 → USD proceeds drop to $4,500,000  
- If spot falls to 0.95 → USD proceeds drop to $4,275,000  

A weaker euro directly reduces revenue, margins, and cash‑flow predictability.

---

## Hedging Strategy Families

### **1. Forward Contract (Sell EUR Forward)**
Lock in a fixed EUR/USD rate for settlement in one year.  
**Pros:** Eliminates FX uncertainty, simple, low cost, perfect timing match  
**Cons:** No upside if EUR strengthens; may require credit line/collateral  

### **2. Options (EUR Put / USD Call)**
Buy the right (not obligation) to sell EUR at a strike price.  
**Pros:** Downside protection, upside retained, flexible structures  
**Cons:** Premium cost, more complex to explain  

### **3. Money Market Hedge**
Borrow the discounted present value of the foreign receivable, convert to USD at spot, invest at domestic interest rate.  
**Pros:** Locks in guaranteed USD value today, no derivatives needed  
**Cons:** Requires balance‑sheet capacity; may not perfectly match timing  

---

## Methods

**Spot Rate:** 1.1517 USD/EUR  
**Receivable Amount:** €4,500,000  

---

### **Forward Hedge**
- **EUR/USD 1‑Year Forward Rate:** **1.0875**  
- **Locked‑in USD Value:**   €4,500,000 times 1.0875 = $4,893,750

**Approach:**  
Enter into a forward contract to sell €4.5M in one year at the predetermined rate, ensuring a fixed USD inflow regardless of market fluctuations.

---

### **Money Market Hedge (Updated Inputs)**  
- **U.S. 1‑Year Interest Rate (domestic):** **3.68%**  
- **EU 1‑Year Interest Rate (foreign):** **2.80%**

**Approach:**  
1. Borrow the present value of €4.5M discounted at the EU interest rate.  
2. Convert the borrowed EUR to USD at today’s spot rate (1.1517).  
3. Invest the USD proceeds at the U.S. interest rate (3.68%).  
4. Use the EUR receivable in one year to repay the EUR loan.  

This locks in a guaranteed USD amount independent of future FX movements.

---

### **Option Hedge **  
- **EUR/USD Put (Call) Strike Price:** **1.15**  
- **Option Premium:** **0.01**

**Approach:**  
Purchase EUR put options (equivalently USD call options) to secure a minimum EUR/USD conversion rate while retaining upside potential if the euro appreciates. The option defines a worst‑case exchange rate while preserving favorable outcomes.

---

## Limitations & Next Steps

### **Limitations**
- Forward hedge removes upside potential.  
- Option hedge may be costly depending on volatility.  
- Money Market hedge depends on borrowing capacity and operational flexibility.  
- All strategies assume full and timely collection of the receivable.

---

### **Next Steps**

#### **Stage 2 — Excel Model Build**
- Compute USD outcomes under spot, forward, money‑market, and option hedges  
- Run scenario and sensitivity analysis (EUR depreciation/appreciation paths)  
- Compare expected value, worst‑case, and best‑case outcomes  
- Produce charts and tables for CFO‑level presentation  

#### **Stage 3 — Technical Specification**
- Model architecture (inputs, assumptions, formulas, outputs)  
- Data flow and calculation logic  
- Required improvements (automation, scenario engine, stress testing)  
- Specification detailed enough for an AI to rebuild the model from scratch  

#### **Stage 4 — Final Analysis & Recommendation**
- Use model results to select the preferred hedge strategy  
- Write a structured AI prompt that reproduces your analysis  
- Prepare a CFO‑ready narrative explaining the exposure, alternatives, and recommendation  

---

## References
Investing.com. (n.d.). *EUR USD Forward Rates*. Retrieved April 2, 2026, from https://www.investing.com/currencies/eur-usd-forward-rates

Euribor . (n.d.). Euribor rates - all information on Euribor. Euribor-Rates.eu. Retrieved April 3, 2026, from https://www.euribor-rates.eu/en/
