# EUR Receivable – Technical Specification

**Created by:** Liam Nelson  
**Updated by:** Liam Nelson  
**Date Created:** 17 April 2026  
**Date Updated:** 17 April 2026  
**Version:** 0.1  
**LLM Used:** Copilot

**Role:** Financial Analyst / Treasury Analyst  
**Audience:** CFO or Director of Treasury  

**Purpose:** Provide a professional, quantitative specification outlining the analytical structure for evaluating FX hedging alternatives for a EUR receivable.

---

## 1. Problem Statement

The company is a U.S.–based solar importing business expecting to **receive EUR 4,500,000 in one year**, as stated in the workbook:

> “US Based Solar importing company to receive $4.5M EUR in one year.”

This creates exposure to **EUR/USD depreciation**, which would reduce the USD value of the receivable. The objective of this specification is to define the analytical framework for quantifying, comparing, and evaluating **forward**, **money market**, and **option‑based** hedging strategies to protect the USD value of the future EUR inflow. The analysis supports corporate treasury decision‑making at the CFO level.

---

## 2. Inputs (Known Variables)

| Variable | Description | Unit | Value | Source |
|---------|-------------|-------|-------:|--------|
| `FC_AMT` | Foreign‑currency receivable | EUR | 4,500,000 | Workbook |
| `S₀` | Current EUR/USD spot rate | USD/EUR | 1.1517 | Workbook |
| `F₀` | 1‑year EUR/USD forward rate | USD/EUR | 1.0875 | Workbook |
| `r_USD` | USD 1‑year interest rate | % | 3.68% | Workbook |
| `r_EUR` | EUR 1‑year interest rate | % | 2.799% | Workbook (foreign rate treated as EUR rate) |
| `t` | Time to maturity | Years | 1 | Derived |
| `K_call` | EUR Call strike | USD/EUR | *Not provided* | Workbook header only |
| `Premium_call` | Call premium | USD per EUR | 0.0143 | Workbook |
| `K_put` | EUR Put strike | USD/EUR | *Not provided* | Not included |
| `Premium_put` | Put premium | USD per EUR | *Not provided* | Not included |

---

## 3. Assumptions & Constraints

Directly from workbook:

- “Interest rates are simple annual rates with no compounding adjustments.”  
- “Borrowing and lending assumed at same stated rate.”  
- “Forward rates assumed arbitrage-free.”  
- “Option premium treated as paid today and grown at domestic rate.”  
- “Hedge outcomes expressed as USD cash outflows in one year.”

Additional assumptions:

- Exchange rates expressed as **USD per EUR**.  
- No transaction costs, bid‑ask spreads, or taxes.  
- Markets assumed perfectly liquid with no borrowing or short‑selling constraints.  
- Future FX scenarios treated as exogenous.  
- For a receivable, the optimal hedge **maximizes USD proceeds**.

---

## 4. Calculation Flow

### 4.1 No Hedge
1. Define a grid of future EUR/USD spot rates \(S_T\).  
2. Compute USD proceeds:  
   

\[
   USD_{NoHedge}(S_T) = FC\_AMT \times S_T
   \]



### 4.2 Forward Hedge
1. Use the provided forward rate \(F_0\).  
2. Compute locked‑in USD proceeds:  
   

\[
   USD_{Forward} = FC\_AMT \times F_0
   \]



### 4.3 Money Market Hedge (Receivable)
1. Discount EUR receivable to present value:  
   

\[
   PV_{EUR} = \frac{FC\_AMT}{1 + r_{EUR}}
   \]


2. Convert PV_EUR to USD at spot:  
   

\[
   USD_0 = PV_{EUR} \times S_0
   \]


3. Invest USD at r_USD.  
4. Compute USD proceeds in one year:  
   

\[
   USD_{MM} = USD_0 \times (1 + r_{USD})
   \]



### 4.4 Option Hedge (EUR Call)
1. Select call strike \(K\).  
2. Compute premium today:  
   

\[
   Premium_0 = FC\_AMT \times Premium\_{call}
   \]


3. Grow premium to one year:  
   

\[
   Premium_1 = Premium_0 \times (1 + r_{USD})
   \]


4. At maturity:  
   - If \(S_T < K\): exercise → receive \(FC\_AMT \times K\)  
   - If \(S_T \ge K\): let expire → receive \(FC\_AMT \times S_T\)
5. Net USD proceeds:  
   

\[
   USD_{Option}(S_T) = USD_{Settlement}(S_T) - Premium_1
   \]



### 4.5 Comparative Analysis
1. Compute USD proceeds for all strategies across all \(S_T\).  
2. Compute hedge P/L vs. no hedge.  
3. Identify the “Winner” (highest USD proceeds).  
4. Summarize trade‑offs:  
   - Forward = certainty  
   - Money market = synthetic forward  
   - Option = upside with protection  

---

## 5. Outputs

| Output | Description | Format | Purpose |
|--------|-------------|---------|----------|
| `USD_forward` | USD proceeds from forward hedge | Numeric | Certainty benchmark |
| `USD_mm` | USD proceeds from money market hedge | Numeric | Cross-check against forward |
| `USD_call` | USD proceeds from EUR call hedge | Table | Optional upside case |
| `USD_put` | *Not applicable* | — | — |
| `Chart_1` | Hedge outcomes vs. S_T | Line chart | Visual comparison |
| `Summary` | Written conclusion | 1–2 paragraphs | Executive-ready takeaway |

---

## 6. Sensitivity Plan

- Vary EUR/USD spot at maturity \(S_T\) from **0.95×S₀ to 1.05×S₀** in increments of **0.01**.  
- For each \(S_T\), compute USD proceeds under:  
  - No hedge  
  - Forward hedge  
  - Money market hedge  
  - Option hedge  
- Present results in:  
  - A comparison table  
  - A line chart showing USD proceeds vs. \(S_T\)

This sensitivity analysis highlights how each hedge performs under EUR appreciation and depreciation.

---

## 7. Limitations & Next Steps

### Limitations
- No implied volatility or option pricing model (premium treated as exogenous).  
- Strike price not provided in workbook.  
- No credit risk, counterparty risk, or liquidity constraints.  
- No hedge accounting considerations.

### Next Steps
1. **Deliver a polished, executive‑ready memo** summarizing the FX hedge analysis and recommending the best strategy.  
2. **Write a structured AI prompt** capable of regenerating the spreadsheet model — demonstrating the ability to convert domain knowledge into machine‑readable instructions.  
3. Use Stage 2 spreadsheet outputs and this specification as the foundation for both deliverables.  
4. Generate a draft using an LLM, then refine it with your own analysis and judgment.  



