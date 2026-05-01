# Executive Memo: EUR Receivable Hedging Strategy & Analysis

**To:** Chief Financial Officer / Director of Treasury
**From:** Liam Nelson, Financial / Treasury Analyst
**Date:** May 1, 2026
**Subject:** Optimal Hedging Strategy for €4,500,000 1-Year Receivable

---

## A. Exposure Summary

Our US-based solar exporting operations are expecting a €4,500,000 cash inflow in 12 months. Because our functional currency is the USD, this foreign currency receivable exposes us to significant FX risk from downward fluctuations in the EUR/USD exchange rate. 

If the Euro depreciates against the Dollar over the next year, our total USD cash inflows will decrease, directly hitting our bottom-line revenue. The objective of this analysis is to evaluate alternative hedging strategies to establish a floor for our USD revenue, mitigate downside risk, and explore opportunities to preserve upside if the Euro strengthens.

---

## B. Summary of Hedge Outcomes

Based on current market data, we evaluated four primary strategies. Here is the strategic overview of our options to protect our USD inflows:

| Strategy | What to Highlight | What to Discuss |
|----------|------------------|-----------------|
| **Forward Hedge** | **Locked-in Proceeds:** ~$4,893,750 | The 1-year forward rate of 1.0875 is trading at a steep discount to the spot rate of 1.1517. While this provides total budget certainty, we lock in a significant opportunity loss compared to current spot levels. |
| **Money Market Hedge** | **High Fixed Yield:** ~$5,227,015 | We synthesize a forward by borrowing EUR at 2.80%, converting at the 1.1517 spot, and investing the USD at 3.68%. Because USD rates are higher, this yields a mathematically superior guaranteed inflow compared to the forward market. |
| **Put Option** | **Downside Floor & Upside Potential** | **Downside:** Costs an upfront premium. **Upside:** Establishes a worst-case scenario floor at the 1.1517 strike while allowing us to capture all market upside if the EUR appreciates. |
| **Call Option** | **Speculative Leverage** | **Upside:** Amplifies our gains if the EUR appreciates (we profit from both the underlying receivable and the call). **Downside:** Costs a premium and provides absolutely zero protection against our primary risk (EUR depreciation). |
| **No Hedge** | **Baseline Risk:** Unlimited downside | Remaining unhedged leaves our revenues completely exposed to market whims. We only benefit if the EUR appreciates significantly above the current spot rate. |

---

## C. Sensitivity Interpretation

To stress-test our strategies, we analyzed the total USD inflows across a range of maturity spot rates (S_T) from 1.0517 to 1.1517+. 

* **EUR Depreciation Scenarios (EUR weakens against USD):** If the Euro drops significantly, the Unhedged position destroys revenue. The Forward and Money Market hedges perfectly insulate us, providing guaranteed inflows regardless of how far the Euro falls. The Put Option successfully kicks in to establish our revenue floor, making it highly valuable here.
* **EUR Appreciation Scenarios (EUR strengthens against USD):** If the Euro rises above the current 1.1517 spot, the Forward and Money Market hedges lock us out of those gains. The Unhedged position performs best, followed closely by the Put Option (which allows us to convert our EUR at the higher market rate, minus the sunk cost of the premium). 

---

## D. Strategic Recommendation

**Recommendation: Execute a Put Option (if volatility is high) or a Money Market Hedge (for guaranteed yield).**

Given the steep forward discount (1.0875), selling our Euros forward is highly unattractive. 

If treasury policy dictates **absolute certainty**, the **Money Market Hedge** is the clear winner for a fixed strategy. By borrowing EUR today, converting at the favorable 1.1517 spot rate, and investing in higher-yielding USD (3.68%), we guarantee an inflow of ~$5.22M, vastly outperforming the Forward Hedge.

If we want to **preserve upside**, purchasing a **Put Option** at the 1.1517 strike is recommended. It secures a high revenue floor while keeping the door open for extra profit if the Euro rallies.

---

## E. Executive Justification

* **Cash Flow Stability:** The recommended hedges prevent our Q4/Q1 revenues from falling below acceptable budgeting thresholds.
* **Yield Optimization:** The Money Market hedge capitalizes on the favorable interest rate differential between the US and the Eurozone, capturing yield that the forward market is currently discounting.
* **Optionality Value:** A Put Option acts as perfect revenue insurance. It protects the downside risk of a collapsing Euro while allowing us to participate in favorable market swings.
* **Liquidity Impact:** It is important to note that the Money Market hedge requires the ability to borrow EUR and ties up USD liquidity in investments for 12 months, whereas the Put Option requires immediate cash outflow for the premium. 

---

### Appendix: Prompt Engineering Deliverable

*Here is the AI prompt designed to regenerate the spreadsheet model, corrected for a receivable exposure.*

**Prompt to Generate Spreadsheet Model:**
> "Act as an expert Financial Modeler and Treasury Analyst. I need to build an FX Hedging Analysis model in Excel for a foreign currency receivable. 
>
> Please generate a structured CSV output or step-by-step Excel formulas based on the following inputs and constraints:
> 
> **Inputs:**
> * Exposure: 4,500,000 EUR Receivable in 1 year.
> * Current Spot (S_0): 1.1517 USD/EUR
> * 1-Year Forward (F_0): 1.0875 USD/EUR
> * Domestic USD Rate: 3.68% (Simple annual)
> * Foreign EUR Rate: 2.80% (Simple annual)
> * EUR Put Option: Strike 1.1517 USD/EUR, Premium 0.0143 USD/EUR.
>
> **Requirements:**
> 1. Calculate the fixed USD inflow of a Forward Hedge (Selling EUR forward).
> 2. Calculate the fixed USD inflow of a Money Market Hedge (Borrow EUR, convert at spot, invest USD). Assume interest is simple and borrowing/lending rates are equal.
> 3. Create a sensitivity data table. Vary the maturity spot rate (S_T) from 1.0517 to 1.2517 in 0.02 increments. 
> 4. For each S_T in the data table, calculate the total USD inflow in 1 year for:
>    - Unhedged Position
>    - Forward Hedge
>    - Money Market Hedge
>    - Put Option Hedge (Remember to deduct the Future Value of the upfront premium, grown at the domestic USD rate).
> 5. Add a final column that outputs the name of the strategy with the highest USD cash inflow for each S_T scenario."
> 6. > **1. Color Coding & Best Practices (Apply strictly):**
> * **Hardcoded Inputs:** Font color MUST be Blue (`#0000FF`) with a light yellow background (`#FFF2CC`).
> * **Calculations/Formulas:** Font color MUST be Black (`#000000`).
> * **Headers/Section Titles:** Bold white font (`#FFFFFF`) with a dark blue or dark gray background (`#203764` or `#404040`).
> * **Conditional Formatting:** In the sensitivity table, highlight the highest USD cash inflow in each row with a light green background (`#E2EFDA`) and dark green text (`#375623`).
> 
> **Layout & Sections:**
> 
> **Title Block**
> * Row 2: "Hedging Foreign Currency Receivables" (Header formatting)
> * Row 3: "US Based Solar operations to receive 4.5M EUR in one year."
>
> **Given Variables**
> * Create columns for: `Description`, `Value`, `Unit`, `Key` (e.g., Editable, Outcome, Formula).
> * *Inputs:* 1-Year Receivable (4,500,000 EUR), Current Spot Rate (1.1517), U.S. Rate (3.68%), Foreign EUR Rate (2.80%), 1-Year Forward (1.0875), Put Strike (1.1517), Put Premium (0.0143), Call Strike (1.1517), Call Premium (0.0143).
>
> **1. Forward Hedge**
> * Row: `[a] Sell EUR/USD 1-Year Forward` (Calculate guaranteed USD inflow). Add a note: "<-- LOCKED IN PROCEEDS".
>
> **2. Money Market Hedge**
> * Row `[a]`: Determine present value of the foreign receivable (Borrow EUR).
> * Row `[b]`: Convert `[a]` into domestic currency at current spot rate.
> * Row `[c]`: Invest `[b]` at domestic USD rate to find future value in 1 year.
>
> **3. Option Hedges**
> * Row `[a]`: Future Value of Put Premium paid today.
> * Row `[b]`: Guaranteed minimum inflow using Put Strike.
> * Row `[c]`: Future Value of Call Premium paid today.
>
> **Sensitivity Analysis (Data Table)**
> * Create a matrix with headers: `S_T (Maturity Spot)`, `0. No Hedge`, `1. Forward Hedge`, `2. Money Market Hedge`, `3. Put Option`, `4. Call Option`, `Hedge Winner`.
> * Vary S_T from 1.0517 to 1.2517 in increments of 0.02 down the rows.
> * Build out the total cash inflow formulas for each column at each S_T level.
> * The `Hedge Winner` column must dynamically output the name of the strategy yielding the highest USD value for that specific row."

## Extra credit answers

### 1. AI Skills & Automation
In modern Corporate Treasury and FP&A roles, static spreadsheets are being replaced by dynamic, AI-augmented scenario analysis. By culminating this project in Stage 4 with a structured **"spec-to-model-to-prompt automation pipeline,"** I have built a system that goes far beyond a one-time calculation. If an AI agent (like Claude with API tools or ChatGPT with Code Interpreter) is fed the Stage 4 prompt alongside the Stage 3 technical specification, it can independently pull live market data—such as real-time EUR/USD spot rates, 1-year forward rates, and Euribor/SOFR interest rates. 

Instead of manually updating hardcoded inputs, the AI can instantly regenerate the entire model on demand. Furthermore, it can take the template and create any future analyses thet I would need. I would just have to change the recievable amounts, and the forward rates.

### 2. GitHub & Version Control
By committing the Stage 1 Memo (the business case), Stage 2 Model (the math), Stage 3 Spec (the rules), and Stage 4 Prompt (the automation instructions) to a GitHub repository, I have established a transparent and auditable history of the financial decision-making process. 
This multi-stage, version-controlled approach ensures total model reproducibility, it can simply pull the Stage 3 and 4 markdown files from GitHub, and rebuild the analysis and spreadsheet.

### 3. Accounting & Audit Integration
A critical component of executing corporate hedges is compliance with accounting standards, such as ASC 815, which accounting firms audit rigorously. To utilize hedgeing where FX gains or losses on the Put Option or Forward contract are temporarily deferred in Other Comprehensive Income (OCI) rather than immediately creating volatility in Net Income, a company must formally document the hedge at inception and provide hedge effectiveness proof.

This repository serves as a perfect artifact for this exact requirement. The Stage 1 Memo and Stage 3 Technical Specification act as the formal hedge accounting documentation, clearly identifying the €4.5M foreign currency receivable as the hedged item and the chosen strategy as the hedging instrument. Furthermore, because these documents are stored in GitHub, the commit history provides an immutable, timestamped audit trail. When auditors review the company's books, the repository serves as evidence that the company executed the hedge based on sound mathematical strategy.




