# Technical Specification: EUR Payable Hedging Analysis

**Created by:** Liam Nelson  
**Updated by:** Liam Nelson  
**Date Created:** April 24, 2026  
**Date Updated:** April 24, 2026  
**Version:** 1.0  
**LLM Used:** Gemini  

**Role:** Financial Analyst / Treasury Analyst  
**Audience:** CFO or Director of Treasury  

**Purpose:** Provide a professional, quantitative specification outlining the analytical structure for evaluating FX hedging alternatives for foreign currency payables.

---

## 1. Problem Statement

Our US-based solar importing company expects to pay €4,500,000 in 12 months, exposing us to potential FX risk from upward fluctuations in the EUR/USD exchange rate. This specification outlines the analytical framework for quantifying, comparing, and evaluating alternative hedging strategies to mitigate that risk and minimize total USD cash outflows.

- **Exposure type:** Foreign Currency Payable  
- **Foreign currency amount and time horizon:** €4,500,000 due in 1 year  
- **Objective:** Protect USD value, cap maximum USD outflow, and minimize costs while preserving downside benefit if the EUR depreciates.  
- **Decision context:** Corporate Treasury  

---

## 2. Inputs (Known Variables)

| Variable | Description | Unit | Example | Source |
|-----------|-------------|------|----------|--------|
| `FC_AMT` | Foreign-currency payable | EUR | 4,500,000 | Company data |
| `S_0` | Current EUR/USD spot rate | USD/EUR | 1.1517 | Market data |
| `F_0` | 1-year EUR/USD forward rate | USD/EUR | 1.0875 | Provided |
| `r_USD` | USD 1-year interest rate (domestic) | % | 3.68% | Market data |
| `r_EUR` | EUR 1-year interest rate (foreign)* | % | 2.80% | Market data |
| `t` | Time to maturity | Years | 1 | Derived |
| `K_call` | EUR Call strike | USD/EUR | 1.1517 | Analyst choice |
| `Premium_call` | Call premium | USD per contract| 0.0143 | Market data |

*(Note: The foreign rate is listed as U.K. interest rate in the source model, serving as the foreign yield for this calculation).*

---

## 3. Assumptions & Constraints

- Interest rates are simple annual rates with no compounding adjustments.  
- Borrowing and lending assumed at the same stated rate.  
- Forward rates assumed arbitrage-free.  
- Bid-ask spreads ignored.  
- Transaction costs excluded.  
- No taxes considered.  
- Option premium treated as paid today and grown at the domestic rate (future value of premium).  
- Markets assumed perfectly liquid.  
- No constraints on borrowing or short-selling.  
- Future FX scenarios treated as exogenous.  
- Hedge outcomes expressed as USD cash outflows in one year.  
- Winner defined as the lowest USD cost under each scenario.  

---

## 4. Calculation Flow

1. **Unhedged Baseline:** Compute the USD cash outflow under an unhedged scenario across varying maturity spot rates ($S_T$).  
2. **Forward Hedge:** Compute fixed USD proceeds/outflow by locking in the 1-year forward rate ($F_0$).  
3. **Money Market Hedge:** - Determine the present value of the foreign payable using the foreign interest rate.
   - Convert this amount into domestic currency (USD) at the current spot exchange rate ($S_0$).
   - Grow this borrowed USD amount by the domestic interest rate to find the total USD outflow at maturity.  
4. **Option Hedge:** Compute outcomes for the EUR Call Option under varying spot outcomes ($S_T$), adding the future value of the call premium paid upfront.  
5. **Scenario Comparison:** Compare the total USD cash outflows across all four strategies (Unhedged, Forward, Money Market, Option).  
6. **Determine Optimal Strategy:** Evaluate and flag the "Winner" (lowest USD cost) for each exogenous spot rate scenario.

---

## 5. Outputs

| Output | Description | Format | Purpose |
|---------|--------------|---------|----------|
| `USD_unhedged` | USD outflow from remaining unhedged | Table | Baseline risk assessment |
| `USD_forward` | USD outflow from forward hedge | Numeric | Certainty benchmark |
| `USD_mm` | USD outflow from money market hedge | Numeric | Alternative fixed-cost benchmark |
| `USD_call` | USD outflow from EUR call hedge | Table | Sensitivity & capped protection |
| `Hedge_Winner` | Strategy with the lowest USD cost | Text | Direct recommendation per scenario |
| `Chart_1` | Hedge outcomes vs. $S_T$ | Line chart | Visual comparison of total USD costs |
| `Summary` | Written conclusion | Paragraph | Executive-ready takeaway |

---

## 6. Sensitivity Plan

> Vary the EUR/USD spot rate at maturity ($S_T$) from 1.0517 to 1.1517+ in incremental steps.  
> For each rate, compute the total USD outflows under the Unhedged, Forward Hedge, Money Market Hedge, and Option Hedge strategies.  
> Present the results as a side-by-side comparison matrix and plot them on a line chart to visualize cost crossovers and identify the winning strategy under each FX regime.

---

## 7. Limitations & Next Steps

> This specification does not incorporate implied volatility dynamics, bid-ask spreads, transaction costs, or taxes, relying on the assumption of perfectly liquid and frictionless markets. 
> 
> The immediate next step is to finalize the Excel model build using this specified logic to quantify exactly what the USD cash outflows will be under each structure and to automatically determine the lowest-cost strategy across all future spot rate scenarios.
