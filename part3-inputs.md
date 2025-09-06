
# The Ultimate Multifamily Pro Forma Guide

## Part 3: Inputs — Rent Roll, Vacancy, Expenses, and Financing

### 1) Rent Roll

**Why It Matters**  
The rent roll drives GPR and therefore EGI, NOI, DSCR, and value. Precision here matters.

**Definition**  
A schedule of units by type and rent level, multiplied by counts and adjusted for term/lease status as needed.

Simple: This is the full list of units and their rents. It shows the total rent if all units were occupied, like a roster that adds up everyone’s ticket price.

**Key Terms**  
- **Unit mix**: counts by floor plan (studio/1BR/2BR).  
- **Market rent vs in‑place rent**: achievable vs current signed rents.  
- **Loss‑to‑lease**: difference between market and in‑place rents.

**Formula**  
```math
\text{GPR(monthly)} = \sum_i (\text{Units}_i \times \text{Rent}_i)
\quad \Rightarrow \quad \text{GPR(annual)} = \text{GPR(monthly)} \times 12
```

**Excel Equivalent**  
```excel
=SUMPRODUCT(Units, RentPerUnit) * 12
```

**Example 1 — 20 Units**  
- 10 @ $1,200; 10 @ $1,400 → GPR = (12,000 + 14,000)*12 = **$312,000**

**Example 2 — 100 Units**  
- 40 @ $1,500; 60 @ $2,000 → GPR = (60,000 + 120,000)*12 = **$2,160,000**

---

### 2) Vacancy Assumptions

**Why It Matters**  
Vacancy materially reduces collectible income; using realistic market vacancy is essential for lender underwriting and investor credibility.

**Definition**  
Percent of GPR assumed uncollected due to unoccupied units and/or non‑payment.

Simple: This is the rent you assume will be lost because some units are empty or unpaid. It’s like planning for some empty seats in a theater—you don’t expect 100% attendance.

**Key Terms**  
- **Physical vacancy** vs **economic vacancy**.  
- **Concessions**: rent discounts used in leasing promotions.

**Formula**  
```math
\text{Vacancy/Credit Loss} = \text{GPR} \times \text{Vacancy Rate}
\quad ; \quad \text{EGI} = \text{GPR} - \text{Vacancy} + \text{Other Income}
```

**Excel Equivalent**  
```excel
=GPR * VacancyRate
```

**Example 1 — Suburban**  
- GPR **$312,000**; Vacancy **5%** → **$15,600** loss

**Example 2 — Urban**  
- GPR **$2,160,000**; Vacancy **7%** → **$151,200** loss

---

### 3) Expense Ratios (for sanity checks)

**Why It Matters**  
When detailed line‑item data is limited, ratios help sanity‑check OpEx levels.

**Definition**  
Operating expenses as a percent of EGI.

Simple: This shows operating costs as a share of income. It’s like checking if groceries, bills, and gas take half your salary or more—quick test for reasonableness.

**Key Terms**  
- **Stabilized**: normal operations after lease‑up/renovation.  
- **Benchmarking**: comparing to similar properties/markets.

**Formula**  
```math
\text{Expense Ratio} = \frac{\text{OpEx}}{\text{EGI}}
```

**Excel Equivalent**  
```excel
=OperatingExpenses / EGI
```

**Example 1**  
- EGI **$305,400**; OpEx **$120,000** → **39.3%**

**Example 2**  
- EGI **$2,128,800**; OpEx **$920,000** → **43.2%**

---

### 4) Financing Terms

**Why It Matters**  
Debt costs determine DSCR, cash flow to equity, and IRR. Underwriting is often capped by DSCR and LTV.

**Definition**  
Loan amount, interest rate, amortization, term, IO (interest‑only) periods, LTV, LTC.

Simple: These are the loan details—amount, rate, years to pay back. They determine the yearly payment, just like a mortgage sets your monthly housing cost.

**Key Terms**  
- **Mortgage constant**: annual debt service ÷ loan amount.  
- **Refinance**: replacing existing debt, potentially distributing proceeds to equity.

**Core Formulas**  
```math
\text{Monthly Payment} = \text{PMT}(r/12,\ n\times12,\ -L)  \quad\Rightarrow\quad
\text{Annual Debt Service} = 12 \times \text{Monthly Payment}
```
```math
\text{Outstanding Balance at sale year }k = \text{FV}(r/12,\ k\times12,\ \text{PMT},\ -L)
```

**Excel Equivalents**  
```excel
=PMT(Rate/12, AmortYears*12, -LoanAmount) * 12
=FV(Rate/12, YearsHeld*12, PMT(Rate/12, AmortYears*12, -LoanAmount), -LoanAmount)
```

**Example 1 — $2.0M Loan, 5.00%, 25‑yr Amort**  
- Annual DS ≈ **$140,496**; Balance after 5 yrs ≈ **$1,751,000**

**Example 2 — $10.0M Loan, 6.00%, 30‑yr Amort**  
- Annual DS ≈ **$719,460**; Balance after 7 yrs ≈ **$8,946,000**

**Naming & Common Controversies**  
- Whether to size to **LTV** or **DSCR** binding constraint; prudent underwriting uses the lower loan of the two.

**References**  
- Freddie Mac Multifamily — Underwriting basics: https://mf.freddiemac.com/  
- Fannie Mae Multifamily — Loan products: https://multifamily.fanniemae.com/

---

## Section Summary and What’s Next
We specified the **inputs** that feed the building blocks: rent roll → GPR; vacancy → EGI; expense ratio/detail → OpEx; financing → debt service and loan balance.  
**Next:** Part 4 covers **adjacent/granular concepts** that refine results and align conventions with lenders and investors.
