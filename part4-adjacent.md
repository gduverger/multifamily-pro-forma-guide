
# The Ultimate Multifamily Pro Forma Guide

## Part 4: Adjacent and Granular Concepts

### 1) Replacement (CapEx) Reserves
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
**What**: Actual historical income/expense for the last 12 months; forms the baseline for stabilization assumptions.  
**Uses**: Normalize one‑time items, trend taxes, and reconcile to forward pro forma.  
**Examples**  
- Removing a **one‑off roof leak** repair from T12 and converting to reserves.  
- Truing‑up **property taxes** to purchase‑price‑based reassessment where applicable.

---

### 3) Exit Assumptions (Sale Price, Costs, Loan Payoff)
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
**What**: Systematic “what‑if” tests for key drivers (rent growth, vacancy, OpEx, exit cap, interest rates).  
**Excel**: Data Table, Scenario Manager, and index‑based drivers.  
**Examples**  
- **Exit Cap ±50 bps** changes value materially (e.g., 5.5% → 6.0% reduces value ~8.3%).  
- **Rent Growth ±1%** shifts IRR several hundred basis points in value‑add deals.

---

### 5) Break‑Even Metrics
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
**What**: Decide whether rents/expenses grow in **nominal** terms (include inflation) or **real** terms (inflation‑adjusted). Keep consistent with discount rates.  
**Note**: Many pro formas are nominal (explicit growth rates plus nominal discount rates).

---

### 7) Taxes & Depreciation (Context Only)
Pro formas in this guide are **pre‑tax** at the property level. Investor‑level tax modeling (e.g., MACRS depreciation, passive loss limits) is complex and outside scope. Coordinate with a CPA.

---

## Section Summary and What’s Next
We covered **conventions** that shape outcomes: reserves policy, T12 baselining, exit value mechanics, sensitivities, break‑even metrics, and real vs nominal choices.  
**Next:** Part 5 summarizes the full pyramid and points to further resources.
