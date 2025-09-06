
# The Ultimate Multifamily Pro Forma Guide

## Part 1: Start from the End — The Top-Level Metrics

### 1) Internal Rate of Return (IRR)

**Why It Matters**  
IRR is a single annualized return that accounts for the *timing* and *magnitude* of all cash flows—periodic cash distributions and the sale—relative to the initial equity invested. It is widely used to compare deals with different cash‑flow patterns and hold periods.

**Definition**  
IRR is the discount rate that sets the net present value (NPV) of all equity cash flows equal to zero.

Simple: This shows the average yearly return from the investment. Think of it like comparing the property’s performance to a stock or bond: it tells you what percent you earn each year, once all money in and out is counted.

**Key Terms**  
- **Cash flow**: net money distributed to equity after operating expenses, reserves (if modeled), and debt service.  
- **Sales proceeds**: net cash to equity at sale after paying selling costs and the outstanding loan balance.  

**Formula**  
```math
0 = \sum_{t=0}^{N} \frac{CF_t}{(1+\text{IRR})^t} \quad\text{with}\quad CF_0 < 0
```

**Excel Equivalent**  
```excel
=IRR(A1:A8)     // A1..A8 contain CF0..CF7 (CF0 negative)
```

**Example 1 — 20‑Unit Property (5‑Year Hold)**  
- Equity (CF0): **–$1,000,000**  
- Years 1–5 distributions: **$80,000** each year  
- Year‑5 sale proceeds to equity: **$1,300,000**  
- Vector: –1,000,000; 80,000; 80,000; 80,000; 80,000; 1,380,000 → **IRR ≈ 12.4%**

**Example 2 — 100‑Unit Property (7‑Year Hold)**  
- Equity (CF0): **–$5,000,000**  
- Years 1–7 distributions: **$400,000** each year  
- Year‑7 sale proceeds to equity: **$6,200,000**  
- Vector: –5,000,000; 400,000×6; 6,600,000 → **IRR ≈ 14.6%**

**Naming & Common Controversies**  
- Whether to include **reserves** as cash outflows before IRR (best practice: yes, if they’re actually funded).  
- Whether to model **sale costs** explicitly (best practice: yes, as a % of sale price).

**References**  
- Investopedia — IRR overview: https://www.investopedia.com/terms/i/irr.asp  
- CCIM Institute — Financial Analysis: https://www.ccim.com/resources/financial-analysis/

---

### 2) Cash‑on‑Cash Return (CoC)

**Why It Matters**  
CoC is a simple first‑year (or period‑specific) yield measure: how much pre‑tax cash an investor receives relative to the equity invested. It’s intuitive for gauging near‑term income.

**Definition**  
Annual pre‑tax cash flow divided by total equity invested (period‑specific, commonly Year‑1).

Simple: This tells you how much cash you earn in one year compared to what you invested. It’s like checking the interest you get on a savings account, but for property cash flow.

**Key Terms**  
- **Equity invested**: total cash contributed by investors at closing (and subsequent capital calls, if any).  
- **Pre‑tax cash flow**: cash after operating expenses, reserves (if modeled), and debt service, before income taxes.

**Formula**  
```math
\text{CoC}_t = \frac{\text{Pre‑Tax Cash Flow in period } t}{\text{Total Equity Invested}}
```

**Excel Equivalents**  
```excel
=Annual_CashFlow / Equity_Invested
=INDEX(CashFlows, t) / Equity_Invested
```

**Example 1 — Suburban Asset**  
- Equity: **$1,200,000**; Year‑1 pre‑tax cash flow: **$96,000** → **CoC = 8.0%**

**Example 2 — Urban Asset**  
- Equity: **$2,500,000**; Year‑1 pre‑tax cash flow: **$175,000** → **CoC = 7.0%**

**Naming & Common Controversies**  
- Some report **stabilized CoC** (first “steady‑state” year) vs **Year‑1 CoC** (may be depressed during lease‑up). State which you use.

**References**  
- NAIOP — Investment metrics primer: https://www.naiop.org/  
- ULI — Research: https://uli.org/research/

---

### 3) Equity Multiple (EM)

**Why It Matters**  
EM measures *total* money back to equity relative to money in. It ignores timing but communicates overall magnitude of return.

**Definition**  
Total cash returned to equity (including sale) divided by total equity invested.

Simple: This shows how many dollars you get back in total for each dollar you put in. For example, putting in $1 and getting back $2 means a 2.0x multiple. It’s like looking at the scale of return without caring about time.

**Key Terms**  
- **Total distributions**: all periodic distributions plus net sale proceeds to equity.

**Formula**  
```math
\text{EM} = \frac{\sum_{t=1}^{N} \text{Distributions}_t + \text{Sale Proceeds}}{\text{Total Equity Invested}}
```

**Excel Equivalents**  
```excel
=SUMIF(CF_range,">0") / ABS(INDEX(CF_range,1))     // if CF0 is the only negative
=SUMPOS(CF_range)/SUMNEGABS(CF_range)              // with custom helpers
```

**Example 1 — Value‑Add**  
- Equity: **$1,500,000**; Total back over 6 years: **$3,000,000** → **EM = 2.0x**

**Example 2 — Core**  
- Equity: **$4,000,000**; Total back over 10 years: **$6,400,000** → **EM = 1.6x**

**Naming & Common Controversies**  
- Clarify whether you include **refinance proceeds** as distributions (many do).

**References**  
- Investopedia — Equity Multiple: https://www.investopedia.com/terms/e/equity-multiple.asp  
- NCREIF — Performance metrics: https://www.ncreif.org/

---

### 4) Debt Service Coverage Ratio (DSCR)

**Why It Matters**  
DSCR is a primary lender constraint indicating the cushion of income over debt service.

**Definition**  
NOI divided by annual debt service (principal + interest).

Simple: This shows if the property’s income is enough to cover loan payments with a margin of safety. Banks view it like a stress test: above 1.0 means income is bigger than debt payments, leaving cushion.

**Key Terms**  
- **NOI**: income after operating expenses, before debt service and taxes.  
- **Debt service**: scheduled annual mortgage payments.

**Formula**  
```math
\text{DSCR} = \frac{\text{NOI}}{\text{Annual Debt Service}}
```

**Excel Equivalents**  
```excel
=NOI / Debt_Service
=NOI / (PMT(rate/12, amort*12, -LoanAmount)*12)
```

**Example 1 — Conservative Leverage**  
- NOI **$900,000**; Debt service **$700,000** → **DSCR = 1.29**

**Example 2 — Aggressive Leverage**  
- NOI **$800,000**; Debt service **$720,000** → **DSCR = 1.11**

**Naming & Common Controversies**  
- Lenders often require **1.20–1.25x** minimum; some use **Underwritten NOI** (with haircuts to rents/other income).

**References**  
- HUD Multifamily — Programs & underwriting: https://www.hud.gov/program_offices/housing/mfh  
- Investopedia — DSCR: https://www.investopedia.com/terms/d/dscr.asp

---

## Section Summary and What’s Next

We covered the four **top‑level outputs** that drive investment decisions: **IRR, CoC, EM, and DSCR**—including definitions, Excel equivalents, examples, and common modeling choices.  

**Next:** Part 2 steps down into the **building blocks (EGI, NOI, Operating Expenses)** that produce these outputs.
