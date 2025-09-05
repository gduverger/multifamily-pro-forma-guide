
# The Ultimate Multifamily Pro Forma Guide

## Part 5: Summary and Next Steps

### What We Learned (Pyramid Recap)
1. **Top Outputs (Part 1)**:  
   - **IRR** (timing‑aware return), **CoC** (period yield), **EM** (total multiple), **DSCR** (lender cushion).  
2. **Building Blocks (Part 2)**:  
   - **EGI → OpEx → NOI** as the core operating engine.  
3. **Inputs (Part 3)**:  
   - **Rent roll** builds **GPR**; **vacancy** reduces to **EGI**; **expense detail/ratios** form **OpEx**; **financing** sets **debt service** and **loan payoff**.  
4. **Adjacent Concepts (Part 4)**:  
   - **Reserves**, **T12 normalization**, **exit price mechanics**, **sensitivity**, **break‑even**, and **real vs nominal** choices.

### Minimal Working Model (Step‑By‑Step)
1. **Unit mix & market rents →** `GPR = SUMPRODUCT(Units, Rent) * 12`  
2. **Vacancy/credits →** `EGI = GPR - Vacancy + OtherIncome`  
3. **OpEx →** `NOI = EGI - OpEx`  
4. **Debt service →** `DS = PMT(r/12, n*12, -Loan)*12`  
5. **Value @ exit →** `Sale = NOI_exit / ExitCap` and `NetToEquity = Sale - SellCosts - LoanBal`  
6. **Outputs →** `DSCR = NOI/DS`, `CoC = CF1/Equity`, `EM = SUMPOS(CF)/ABS(CF0)`, `IRR = IRR(CF_range)`

### Common Naming/Assumption Flags
- **Reserves in/out of NOI** — state your convention.  
- **Stabilized vs Year‑1** — state which your CoC/NOI reflect.  
- **Nominal vs Real** growth and discount rates — be consistent.  
- **Exit cap** and **selling costs** — disclose clearly.

### Further Reading & References
- Investopedia — IRR, NOI, EGI, DSCR primers: https://www.investopedia.com/  
- CCIM Institute — Financial Analysis: https://www.ccim.com/resources/financial-analysis/  
- ULI — Research: https://uli.org/research/  
- NCREIF — Performance metrics: https://www.ncreif.org/  
- Freddie Mac Multifamily: https://mf.freddiemac.com/ | Fannie Mae Multifamily: https://multifamily.fanniemae.com/  
- BOMA — Expense categories/benchmarking: https://www.boma.org/

### Closing
You should now be able to read and build a multifamily pro forma, trace **inputs → building blocks → outputs**, and explain key modeling choices to lenders and investors. For advanced work, extend the model with **lease‑up schedules, renovation programs, refinance scenarios, and tax‑aware investor waterfalls**.
