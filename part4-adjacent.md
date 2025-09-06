
# The Ultimate Multifamily Pro Forma Guide

## Part 4: Adjacent and Granular Concepts

### 1) Replacement (CapEx) Reserves
Simple: Money set aside each year for big future fixes (roof, heating system). It’s like saving for a new car—you don’t buy it every year, but you plan ahead.
**What**: Budget set aside annually for future major replacements (roof, boilers, parking lots).  
**Where in model**: Often **below NOI** (i.e., not part of OpEx) but subtracted before distributions to equity; some lenders include a minimum reserve in underwriting.  
**Excel**  
```excel
=Annual_Reserve
```
**Examples**  
- **$300/unit/year** for a 100‑unit → **$30,000** per year.  
- **$250/unit/year** for 24 units → **$6,000** per year.  
**Reference**: Freddie Mac/Fannie Mae underwriting guides (reserve minima).

---

### 2) T12 (Trailing‑12‑Month) Financials
Simple: The last 12 months of actual income and costs. It’s like looking at your bank statements for the past year to see your real spending and earnings.
**What**: Actual historical income/expense for the last 12 months; forms the baseline for stabilization assumptions.  
**Uses**: Normalize one‑time items, trend taxes, and reconcile to forward pro forma.  

**Formula / Excel (when applicable)**  
No single formula. In Excel, sum the last 12 months of each line item (e.g., `=SUM(B2:M2)` for months Jan–Dec). Trend or normalize as needed.
**Examples**  
- Removing a **one‑off roof leak** repair from T12 and converting to reserves.  
- Truing‑up **property taxes** to purchase‑price‑based reassessment where applicable.

---

### 3) Exit Assumptions (Sale Price, Costs, Loan Payoff)
Simple: These are the numbers for selling the property at the end: sale price, costs to sell, and remaining loan. The result is the net cash left for investors.
**Formulas**  
```math
\text{Sale Price at Exit} = \frac{\text{NOI}_{exit}}{\text{Exit Cap Rate}}
```
```math
\text{Net Sale Proceeds to Equity} = \text{Sale Price} - \text{Selling Costs} - \text{Loan Balance at Sale}
```
**Excel Equivalents**  
```excel
=NOI_exit / ExitCap
=SalePrice - (SalePrice*SellCost%) - LoanBalanceExit
```
**Examples**  
- NOI_exit **$1,300,000**, Exit cap **5.50%**, Selling costs **2.5%**, Loan balance **$8.95M** →  
  Sale **$23.64M**, Net to equity **$14.09M** (approx.).  
- NOI_exit **$900,000**, Exit cap **6.00%**, Selling costs **3.0%**, Loan balance **$11.2M** →  
  Sale **$15.00M**, Net to equity **$3.35M** (approx.).  
**Controversies**: Whether to model **cap rate expansion** (e.g., +25–50 bps) and the level of **selling costs** (commonly 1.5–3.0%+ by market/deal size).

---

### 4) Sensitivity & Scenario Analysis
Simple: This is testing ‘what if’ questions, like what happens if rents grow slower or if the sale price is lower. It’s like adjusting ingredients in a recipe to see how the taste changes.
**What**: Systematic “what‑if” tests for key drivers (rent growth, vacancy, OpEx, exit cap, interest rates).  
**Excel**: Data Table, Scenario Manager, and index‑based drivers.  
**Examples**  

**Excel Equivalent (when applicable)**  
Use Excel **Data Table** or **Scenario Manager**. For a one‑way table, link the output cell and vary a single input. For a two‑way table, vary two inputs across rows and columns.
- **Exit Cap ±50 bps** changes value materially (e.g., 5.5% → 6.0% reduces value ~8.3%).  
- **Rent Growth ±1%** shifts IRR several hundred basis points in value‑add deals.

---

### 5) Break‑Even Metrics
Simple: These show the point where income just covers costs and debt. It’s like figuring out how many hours you must work to cover rent and food before any savings.
**Formulas**  
```math
\text{Break‑Even Occupancy} = \frac{\text{OpEx} + \text{Debt Service}}{\text{GPR} + \text{Other Income}}
```
```math
\text{Debt Yield} = \frac{\text{NOI}}{\text{Loan Amount}}
```
**Excel**  
```excel
=(OpEx + DebtService) / (GPR + OtherIncome)
=NOI / LoanAmount
```
**Examples**  
- OpEx **$900k**, DS **$700k**, GPR+Other **$2.2M** → Break‑Even Occ **72.7%**.  
- NOI **$1.25M** on **$15.0M** loan → **Debt Yield 8.3%**.

---

### 6) Real vs Nominal Modeling
Simple: Nominal numbers include inflation; real numbers remove it. It’s like comparing today’s dollars versus what they buy in the future. Be consistent when you discount or grow numbers.
**What**: Decide whether rents/expenses grow in **nominal** terms (include inflation) or **real** terms (inflation‑adjusted). Keep consistent with discount rates.  
**Note**: Many pro formas are nominal (explicit growth rates plus nominal discount rates).

**Formula**  
\( 1 + r_{real} = \frac{1 + r_{nominal}}{1 + \pi} \) → \( r_{real} \approx \frac{1 + r_{nominal}}{1 + \pi} - 1 \)

**Excel Equivalent**  
`=(1+NominalRate)/(1+InflationRate)-1`

---

### 7) Taxes & Depreciation (Context Only)
Simple: This guide stops at property cash flow before taxes. Personal taxes depend on each investor, like how different workers face different tax brackets.
Pro formas in this guide are **pre‑tax** at the property level. Investor‑level tax modeling (e.g., MACRS depreciation, passive loss limits) is complex and outside scope. Coordinate with a CPA.

**Formula / Excel (applicability)**  
Not modeled here at the property level. Investor‑level tax schedules depend on each investor and are outside this guide.

---

## Section Summary and What’s Next
We covered **conventions** that shape outcomes: reserves policy, T12 baselining, exit value mechanics, sensitivities, break‑even metrics, and real vs nominal choices.  
**Next:** Part 5 summarizes the full pyramid and points to further resources.
