
# The Ultimate Multifamily Pro Forma Guide

## Part 1: Start from the End — The Top-Level Metrics

### 1) Internal Rate of Return (IRR)

**Definition**: _IRR is the discount rate that sets the net present value (NPV) of all equity cash flows equal to zero._

In other words, it’s the rate of return that makes the investment “break even” in today’s dollars. This shows the average yearly return from the investment. Think of it like comparing the property’s performance to a stock or bond: it tells you what percent you earn each year, once all money in and out is counted.

**Why It Matters**  
IRR is a single annualized return that accounts for the *timing* and *magnitude* of all cash flows (periodic cash distributions and the sale) relative to the initial equity invested (the money investors put in out of pocket, not the bank’s loan money). It is widely used to compare deals with different cash‑flow patterns and hold periods.

**Key Terms** 
- **Equity**: the cash that the investors themselves put into the deal at the start (their own money, not borrowed from a bank). It’s often called “equity invested” or “investor equity.” 
- **Cash flow (CF)**: net money distributed to equity (i.e., it’s given out to the owners/investors in proportion to their ownership) after operating expenses, reserves (if modeled), and debt service.  
- **Sales proceeds**: net cash to equity (owners/investors) at sale after paying selling costs and the outstanding loan balance.
- **Present value**: how much a future amount of money is worth today, once you adjust for time. Money in the future is worth less than money today (because you could invest today’s money, or inflation erodes value).
- **Reserves**: money the property sets aside each year for future big expenses (new roof, replacing boilers or HVAC systems, repaving the parking lot), not for day-to-day operations.
- **Sales costs (selling costs)**: the transaction expenses you pay when you sell the property (broker commission, legal fees, transfer taxes).

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
- Vector: –1,000,000; 80,000; 80,000; 80,000; 80,000; 1,380,000 → **IRR ≈ 12.66%**

In simple terms, investing $1M gives $80k yearly plus $1.3M at sale, about a 13% yearly return.

**Example 2 — 100‑Unit Property (7‑Year Hold)**  
- Equity (CF0): **–$5,000,000**  
- Years 1–7 distributions: **$400,000** each year  
- Year‑7 sale proceeds to equity: **$6,200,000**  
- Vector: –5,000,000; 400,000×6; 6,600,000 → **IRR ≈ 14.6%**

Another way to say it is, $5M invested returns $400k yearly and $6.2M at sale, close to 15% per year.

**Naming & Common Controversies**  
- Whether to include **reserves** as cash outflows before IRR (best practice: yes, if they’re actually funded).  
- Whether to model **sale costs** explicitly (best practice: yes, as a % of sale price).

**References**  
- Investopedia — IRR overview: https://www.investopedia.com/terms/i/irr.asp  
- CCIM Institute — Financial Analysis: https://www.ccim.com/resources/financial-analysis/

---

### 2) Cash‑on‑Cash Return (CoC)

**Definition**: _Annual pre‑tax cash flow divided by total equity invested (period‑specific, commonly Year‑1)._

Said differently, this tells you how much cash you earn in one year compared to what you invested (while IRR measures your total annualized return over the full investment including timing and sale proceeds). It’s like checking the interest you get on a savings account, but for property cash flow.

Technically, CoC can be shown for any year (Year-2, stabilized Year-3, etc.) or even as an average across the hold. But when someone just says “CoC,” it usually defaults to Year-1 unless specified. Some models also show a “stabilized CoC” once the property reaches steady operations after renovations/lease-up.

**Why It Matters**  
CoC is a simple first‑year (or period‑specific) yield measure: how much pre‑tax cash an investor receives relative to the equity invested. It’s intuitive for gauging near‑term income.

**Key Terms**  
- **Equity invested**: total cash contributed by investors at closing (and subsequent capital calls, if any).  
- **Pre‑tax cash flow**: cash after operating expenses, reserves (if modeled), and debt service, before income taxes.
- **Lease-up**: the period right after acquisition or construction when units are still being rented out and occupancy is ramping up.

**Formula**  
```math
\text{CoC}_t = \frac{\text{Pre‑Tax Cash Flow in period } t}{\text{Total Equity Invested}}
```

**Excel Equivalents**  
```excel
=AnnualCashFlow / EquityInvested
=INDEX(CashFlows, t) / EquityInvested
```

**Example 1 — Suburban Asset**  
- Equity: **$1,200,000**
- Year‑1 pre‑tax cash flow: **$96,000** → **CoC = 8.0%**

Put plainly, $1.2M invested earns $96k in year one, an 8% return.

**Example 2 — Urban Asset**  
- Equity: **$2,500,000**
- Year‑1 pre‑tax cash flow: **$175,000** → **CoC = 7.0%**

Said differently, $2.5M invested earns $175k in year one, a 7% return.

**Naming & Common Controversies**  
- Some report **stabilized CoC** (first “steady‑state” year) vs **Year‑1 CoC** (may be depressed during lease‑up). Year-1 CoC might understate true performance because early cash flow is reduced while the property fills up with tenants. State which you use.

**References**  
- NAIOP — Investment metrics primer: https://www.naiop.org/  
- ULI — Research: https://uli.org/research/

---

### 3) Equity Multiple (EM)

**Definition**: _Total cash returned to equity (including sale) divided by total equity invested._

Another way to say it is, this shows how many dollars you get back in total for each dollar you put in. For example, putting in $1 and getting back $2 means a 2.0x multiple. It’s like looking at the scale of return without caring about time.

**Why It Matters**  
EM measures *total* money back to equity relative to money in. It ignores timing but communicates overall magnitude of return.

**Key Terms**  
- **Total distributions**: all periodic distributions plus net sale proceeds to equity.
- **Refinance proceeds**: the extra cash investors receive when a new loan is taken out that’s larger than the old loan payoff.

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
- Equity: **$1,500,000**
- Total back over 6 years: **$3,000,000** → **EM = 2.0x**

In simple terms, $1.5M becomes $3M over 6 years, doubling the investment (2.0x multiple).

**Example 2 — Core**  
- Equity: **$4,000,000**
- Total back over 10 years: **$6,400,000** → **EM = 1.6x**

Another way to say it is, $4M grows to $6.4M over 10 years, a 1.6x multiple.

**Naming & Common Controversies**  
- Clarify whether you include **refinance proceeds** as distributions (many do). Because refinance is uncertain (depends on market conditions and lender appetite), it’s not guaranteed cash. Including it inflates EM and IRR compared to a no-refi case. That’s why good practice is to disclose (“EM including refinance proceeds = 2.0x” vs “EM excluding refinance proceeds = 1.6x”).

**References**  
- Investopedia — Equity Multiple: https://www.investopedia.com/terms/e/equity-multiple.asp  
- NCREIF — Performance metrics: https://www.ncreif.org/

---

### 4) Debt Service Coverage Ratio (DSCR)

**Why It Matters**  
DSCR is a primary lender constraint indicating the cushion of income over debt service.

**Definition**: _NOI divided by annual debt service (principal + interest)._

Put plainly, This shows if the property’s income is enough to cover loan payments with a margin of safety. Banks view it like a stress test: above 1.0 means income is bigger than debt payments, leaving cushion.

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
Put plainly, income is 29% higher than the $700k debt cost, showing strong coverage.

**Example 2 — Aggressive Leverage**  
- NOI **$800,000**; Debt service **$720,000** → **DSCR = 1.11**
Said differently, income barely covers the $720k debt with only 11% cushion, making it riskier.

**Naming & Common Controversies**  
- Lenders often require **1.20–1.25x** minimum; some use **Underwritten NOI** (with haircuts to rents/other income).

**References**  
- HUD Multifamily — Programs & underwriting: https://www.hud.gov/program_offices/housing/mfh  
- Investopedia — DSCR: https://www.investopedia.com/terms/d/dscr.asp

---

## Section Summary and What’s Next

We covered the four **top‑level outputs** that drive investment decisions: **IRR, CoC, EM, and DSCR**—including definitions, Excel equivalents, examples, and common modeling choices.  

**Next:** Part 2 steps down into the **building blocks (EGI, NOI, Operating Expenses)** that produce these outputs.
