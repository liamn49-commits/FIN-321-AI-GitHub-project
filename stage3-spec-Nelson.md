# GBP Payable – FX Hedging Technical Specification
Created by: Liam Nelson  
Updated by: Liam Nelson  
Date Created: 17 April 2026  
Date Updated: 17 April 2026  
Version: 0.1  
LLM Used: Copilot  

> “Suppose … Solar Equipment Importer a USD-based firm expecting $4.5 Million EUR receivable in 1 year.”  
> “Hedge outcomes expressed as USD cash outflows in one year.”

---

## 1. Problem Statement

The company has a **foreign‑currency payable of GBP 5,000,000** due in **one year**, creating exposure to movements in the **GBP/USD** exchange rate at settlement. If GBP appreciates, the USD cost of the payable increases, reducing cash flow and potentially affecting program‑level margins.

This specification defines the analytical structure for evaluating **forward**, **money market**, and **option‑based** hedging strategies to minimize the USD cash outflow while balancing certainty and upside participation. The analysis supports **corporate treasury** decision‑making at the CFO/Director of Treasury level.

---

## 2. Inputs (Known Variables)

### 2.1 Core Variables

| Variable | Description | Unit | Value | Source |
|---------|-------------|-------|-------:|--------|
| FC_AMT | Foreign‑currency payable | GBP | 5,000,000 | Contract |
| S₀ | Current GBPUSD spot rate | USD/GBP | 1.1517 | Workbook |
| r_USD | U.S. 1‑year interest rate | Annual % | 3.68% | Workbook |
| r_GBP | U.K. 1‑year interest rate | Annual % | 2.799% | Workbook |
| t | Time to maturity | Years | 1 | Contract tenor |

### 2.2 Forward & Option Variables

| Variable | Description | Unit | Value / Status | Notes |
|----------|-------------|-------|----------------|-------|
| F₀_GBP | 1‑year GBPUSD forward rate | USD/GBP | To be sourced | Arbitrage‑free assumption |
| K_CALL_GBP | GBP call strike | USD/GBP | To be set (baseline = S₀) | Analyst choice |
| Premium_CALL_GBP | Call premium per GBP | USD/GBP | 0.0143 | Workbook placeholder |

### 2.3 Scenario Inputs

| Variable | Description | Unit | Value | Notes |
|----------|-------------|-------|--------|-------|
| S_T_grid | Future GBPUSD spot scenarios | USD/GBP | Range around S₀ | Workbook reference |
| T_DAYS | Days to settlement | Days | 365 | Simple annual basis |

---

## 3. Assumptions & Constraints

> “Interest rates are simple annual rates with no compounding adjustments.”  
> “Borrowing and lending assumed at same stated rate.”  
> “Forward rates assumed arbitrage-free.”  
> “Option premium treated as paid today and grown at domestic rate.”

**Modeling conventions**

- Simple annual interest rates; no compounding  
- Forward rate consistent with interest rate parity  
- No bid–ask spreads, transaction costs, or taxes  
- Unlimited borrowing/lending; perfectly liquid markets  
- All hedge outcomes expressed as **USD cash outflows in one year**  
- Option premium paid today and grown at **r_USD**  

---

## 4. Calculation Flow

### 4.1 No Hedge



\[
\text{USD\_NoHedge}(S_T) = \text{FC\_AMT} \times S_T
\]



### 4.2 Forward Hedge



\[
\text{USD\_Forward} = \text{FC\_AMT} \times F_0^{GBP}
\]



### 4.3 Money Market Hedge

Workbook steps:  
> “Determine present value of the foreign payable … Convert … Borrow … Receive in 1-year and make payment.”

1. Discount payable:  
   

\[
   PV_{GBP} = \frac{FC\_AMT}{1 + r_{GBP}}
   \]


2. Convert to USD at spot:  
   

\[
   USD_{0} = PV_{GBP} \times S_0
   \]


3. Borrow USD today.  
4. Repay in one year:  
   

\[
   USD_{MM} = USD_{0} \times (1 + r_{USD})
   \]



### 4.4 Option Hedge (GBP Call)

1. Premium today:  
   

\[
   Premium_0 = FC\_AMT \times Premium\_{CALL}
   \]


2. Future value of premium:  
   

\[
   Premium_1 = Premium_0 \times (1 + r_{USD})
   \]


3. Payoff per GBP:  
   

\[
   Payoff(S_T) = \max(K - S_T, 0)
   \]


4. USD settlement cost:  
   - If exercised: \( FC\_AMT \times K \)  
   - If not: \( FC\_AMT \times S_T \)
5. Total cost:  
   

\[
   USD_{Option}(S_T) = USD_{Settlement}(S_T) + Premium_1
   \]



### 4.5 Comparative Analysis

For each S_T:

- Compute USD_NoHedge, USD_Forward, USD_MM, USD_Option  
- Compute hedge P/L vs. no hedge  
- Identify lowest‑cost strategy (“Winner”)  

---

## 5. Outputs

### 5.1 Numeric Outputs

| Output | Description |
|--------|-------------|
| USD_NoHedge_Base | USD cost at S_T = S₀ |
| USD_Forward | Locked‑in USD cost |
| USD_MM | Synthetic forward cost |
| USD_Option_Base | Option hedge cost at S₀ |
| Premium_1 | FV of option premium |

### 5.2 Scenario Tables

- **USD Cost by Strategy vs. S_T**  
- **Hedge P/L vs. No Hedge**  
- **CFO Summary Table** (S₀, −5%, +5%)  

### 5.3 Charts

- **Line Chart: USD Cost vs. S_T**  
- **Line Chart: Hedge P/L vs. S_T**  

---

## 6. Sensitivity Plan

- Vary S_T from **0.95 × S₀ to 1.05 × S₀** in **0.01 increments**  
- Compute USD cost for all strategies at each S_T  
- Identify:  
  - Where option hedge becomes cheaper than no hedge  
  - Where forward/MM dominate  
  - Where optionality provides value  

---

## 7. Limitations & Next Steps

### Limitations

- No volatility modeling or option pricing  
- No credit or counterparty risk  
- No transaction costs or bid–ask spreads  
- EUR labels in workbook treated as placeholders  

### Next Steps

1. **Deliver a polished, executive‑ready memo** summarizing the FX hedge analysis, interpreting model outputs, and recommending the optimal strategy to senior leadership.

2. **Write a structured AI prompt** capable of regenerating the full spreadsheet model from scratch — demonstrating the ability to translate financial logic into precise, machine‑readable instructions.

3. Use the Stage 2 spreadsheet outputs and Stage 3 technical specification as the foundation for both deliverables, ensuring consistency between quantitative results and narrative interpretation.

4. Generate an initial draft of both the memo and the AI prompt using an LLM, then refine the content using your own financial judgment, ensuring accuracy, clarity, and executive‑level communication.

