
# The Ultimate Multifamily Pro Forma Guide

## Part 2: The Building Blocks — EGI, NOI, and Operating Expenses

### 1) Effective Gross Income (EGI)

**Why It Matters**  
EGI is the *actual* income the property is expected to collect after normal losses; it is the starting point for profitability analysis.

**Definition**  
Potential income from rent (Gross Potential Rent, GPR) adjusted for vacancy and credit loss, plus other income (parking, laundry, storage, RUBS, pet fees).

In simple terms, This is the income the property can really collect after normal losses like empty units or unpaid rent, plus extras like parking or laundry fees. It’s like your paycheck after accounting for missed workdays.

**Key Terms**  
- **GPR**: rent at 100% physical/economic occupancy at market (or in‑place) rents.  
- **Vacancy/Credit loss**: reductions for unoccupied units and non‑payment.  
- **Other income**: non‑rent revenue items.

**Formula**  
```math
\text{EGI} = \text{GPR} - \text{Vacancy/Credit Loss} + \text{Other Income}
```

**Excel Equivalents**  
```excel
=GPR - Vacancy - CreditLoss + OtherIncome
=SUMPRODUCT(Units, MarketRent) * 12 * (1 - VacRate) + OtherIncome
```

**Example 1 — Suburban 20‑Unit**  
- Units: 10 @ $1,200, 10 @ $1,400 → GPR = (10*1,200 + 10*1,400)*12 = **$312,000**  
- Vacancy (5%): **$15,600**; Other income: **$9,000** → **EGI = $305,400**
In simple terms, $312k potential rent is reduced by vacancy, leaving $305k real income.

**Example 2 — Urban 100‑Unit**  
- Units: 40 @ $1,500, 60 @ $2,000 → GPR = (40*1,500 + 60*2,000)*12 = **$2,160,000**  
- Vacancy (7%): **$151,200**; Other income: **$120,000** → **EGI = $2,128,800**
Another way to say it is, $2.16M potential rent becomes $2.13M after vacancy and extras.

**Naming & Common Controversies**  
- Some models include **concessions** explicitly (rent discounts). Keep them separate for clarity.

**References**  
- Investopedia — EGI: https://www.investopedia.com/terms/e/effective-gross-income-egi.asp

---

### 2) Net Operating Income (NOI)

**Why It Matters**  
NOI drives value (via cap rates), loan sizing (via DSCR), and investor returns. It is the core profitability measure before financing and taxes.

**Definition**  
EGI minus operating expenses (excluding debt service, income taxes, and “below‑the‑line” capital expenditures).

Another way to say it is, This is the money left after paying the property’s normal bills but before paying the loan or taxes. It’s like your salary after work expenses but before mortgage and taxes.

**Key Terms**  
- **Operating expenses**: property taxes, insurance, management, payroll, repairs/maintenance, utilities, admin, common area.  
- **Replacement reserves**: some treat these as below‑the‑line (not in NOI); lenders often underwrite a minimum reserve.

**Formula**  
```math
\text{NOI} = \text{EGI} - \text{Operating Expenses}
```

**Excel Equivalent**  
```excel
=EGI - OperatingExpenses
```

**Example 1 — Mid‑Sized Building**  
- EGI **$305,400**; Operating expenses **$120,000** → **NOI = $185,400**
Put plainly, $305k income minus $120k expenses leaves $185k profit.

**Example 2 — Large Complex**  
- EGI **$2,128,800**; Operating expenses **$860,000** → **NOI = $1,268,800**
Said differently, $2.13M income minus $860k expenses leaves $1.27M profit.

**Naming & Common Controversies**  
- Whether **replacement reserves** sit above or below NOI. State your convention and keep it consistent.

**References**  
- Investopedia — NOI: https://www.investopedia.com/terms/n/noi.asp

---

### 3) Operating Expenses (OpEx)

**Why It Matters**  
Small errors in OpEx materially change NOI, DSCR, and value. Benchmarks help validate assumptions.

**Definition**  
Recurring costs to operate the property (taxes, insurance, utilities, payroll, repairs, contract services, management, admin).

Another way to say it is, These are the regular costs to keep the property running: taxes, insurance, utilities, repairs, staff. It’s like the bills a household pays every month to function.

**Key Terms**  
- **Fixed** vs **variable** expenses (taxes/insurance vs utilities/repairs).  
- **Management fee**: commonly 2.5%–4.0% of EGI (varies by market/size).

**Formula (Category Sum)**  
```math
\text{OpEx} = \sum (\text{Taxes} + \text{Insurance} + \text{Utilities} + \text{Repairs} + \text{Payroll} + \text{Mgmt} + \text{Admin} + \text{Other})
```

**Excel Equivalents**  
```excel
=SUM(Taxes,Insurance,Utilities,Repairs,Payroll,Management,Admin,Other)
=EGI * Expense_Ratio      // quick check only
```

**Example 1 — Suburban**  
- Taxes 55k, Insurance 25k, Utilities 18k, Repairs 22k, Mgmt 9k, Admin 6k → **OpEx = $135k**
In simple terms, the suburban property spends $135k yearly to operate.

**Example 2 — Urban**  
- Taxes 420k, Insurance 95k, Utilities 110k, Repairs 135k, Payroll 80k, Mgmt 60k, Admin 20k → **OpEx = $920k**
In simple terms, the suburban property spends $135k yearly to operate.

**Naming & Common Controversies**  
- Use **T12** actuals where possible, adjust to stabilized; document any one‑time items removed.

**References**  
- BOMA — Expense categories: https://www.boma.org/  
- NAIOP — Operating benchmarks: https://www.naiop.org/

---

## Section Summary and What’s Next
We built the middle layer: **EGI → OpEx → NOI**. With NOI in hand, lenders size loans (DSCR) and investors value properties (cap rates).  
**Next:** Part 3 covers the **inputs** (rent roll, vacancy, expense ratios, financing) that feed these building blocks.
