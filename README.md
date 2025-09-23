# 📊 Databel Churn — Power BI Report

This repository contains the final Power BI report built on the Databel churn dataset, plus a story-driven walkthrough of each page.  
It’s written to be skimmable by execs yet useful for analysts.

- **Report:** `Final_Report.pbix`
- **Data:** `Databel - Data.csv`

---

## 🚀 Quick Start
- Open **`Final_Report.pbix`** in Power BI Desktop.
- Use this README to follow the analysis page-by-page.

---

## 🔑 Executive Insights (one page)
- Churn is **front-loaded**: highest in the first few months, then steadily declines (survivorship).
- **Structure beats demographics**: **Month-to-Month** contracts (~46%) and **solo lines** drive most losses; **yearly/two-year** and **group plans** are naturally sticky.
- The **value gap** shows up for **Unlimited** (≈32% vs ~16% non-Unlimited) and for **5–10GB** users (peak risk): classic plan–usage mismatch.
- **International charges** (avg ~33.6) dwarf extra data fees (~3.4) → primary “bill shock” culprit.
- **Support friction** is decisive: churners average **~2–3 calls** vs **~0.3–0.6** for non-churners (4–8× gap) in every state.
- Geography is **mix, not destiny**: hotspots are states with more **intl-active** users + strong local competitors.
- **Payment** is a proxy: **paper check** is riskiest, **credit card** stickiest; direct debit in the middle.
- **Seniors** churn more (complexity/upgrade friction); under-30 cohorts are relatively stable.

---

## 🧭 Report Structure (pages)
1) **Overview & Churn Reasons** — KPIs, age distribution, and reason codes.  
2) **Contracts, Groups & Churn** — contract categories, group size, churn categories.  
3) **Usage × Plan** — Unlimited vs non-Unlimited across usage bands.  
4) **Geography × International** — churn by state + international activity.  
5) **Tenure, Contract & Payment Mix** — hazard curve, contract overlays, payment share.  
6) **Contract Clusters, Tenure & Support** — scatter of tenure vs churn by contract; support volume.  
7) **Charges × Usage × “Unlimited”** — international vs data charges and usage-plan fit.  
8) **State Hotspots, Charges & Support** — where intl fees and repeat contacts cluster.

> The analysis below follows the same order. Each section includes a narrative and a quick TL;DR. Replace image paths if your filenames differ.

---

## 1) Overview & Churn Reasons
![Overview & Churn Reasons](images/Overview.png)

**Narrative**  
What matters isn’t just the churn level; it’s the **shape**. The age curve shows two problems: **volume churn** in the big 30–60 cohorts and **rate churn** that **spikes after ~60**. The “why” splits between **competitive pull** (offers/devices/speeds/data) and **experience push** (support attitude). Price isn’t the headline—**value framing** is. Seniors’ higher churn hints at **upgrade friction + complexity**, while the sizeable “don’t know” bucket signals **passive churn** (lots of small frictions).

**TL;DR:** Rivals win the promise (offers/devices); we lose the moment (support). Mid-life cohorts drive volume; seniors drive rate.

---

## 2) Contracts, Groups & Churn
![Contracts & Groups](images/Contracts_and_Groups.png)

**Narrative**  
Two structural choices explain churn far better than demographics: **contract** and **group size**. Solo lines pay the most per line **and** churn hardest; adding a second line collapses churn into single digits, lifting **household LTV**. Month-to-Month carries ~46% churn vs ~7% for yearly across genders—**who** the customer is matters less than **what** they signed. Nearly half of stated churn is “competitor,” indicating **value packaging** (bundle + device) beats price alone.

**TL;DR:** Churn is a **contract-and-household design** problem—move solos → groups and M2M → annuals.

---

## 3) Usage × Plan (Unlimited vs Non)
![Usage vs Unlimited](images/Usage_vs_Unlimited.png)

**Narrative**  
“Unlimited” isn’t a universal safety net. It carries ~67% of the base and churns at ~32%—**2×** non-Unlimited. The **5–10GB** band is the danger zone for both plan types (peak churn): too much use for the cheapest limited plans, not enough to justify the Unlimited premium. **<5GB** users are sticky on non-Unlimited but churn hard on Unlimited—pure **value mismatch**. Heavy users (≥10GB) are steadier; once usage is truly high, Unlimited’s value is clearer.

**TL;DR:** Churn tracks **value fit**—Unlimited underperforms for light & mid users; 5–10GB is the primary risk zone.

---

## 4) Geography × International Usage
![Churn by State & Intl Usage](images/Geo_and_International.png)

**Narrative**  
Internationally active customers churn at **~34%** vs **~22%** for others—a **+12 pp** lift. Map hotspots are where **travel needs** meet **sharp local competitors**: the geography isn’t causal, the **mix** is. International activity acts as a **risk amplifier** more than a universal problem.

**TL;DR:** Where international needs meet strong local rivals, churn jumps; intl-active adds ~12 points of risk on average.

---

## 5) Tenure, Contract & Payment Mix
![Tenure & Contract](images/Tenure_Contract_Payments.png)

**Narrative**  
The tenure curve is a **hazard + survivorship** story: fragile relationships exit early, leaving a stickier cohort. Contracts **bound** risk—M2M never converges to annual/two-year at any tenure; tenure helps **within** the lane your contract sets. Payment method behaves as a **behavioral proxy**: paper check cohorts are riskiest, credit-card cohorts stickiest; direct debit sits between.

**TL;DR:** Early-life hazard bounded by contract lanes; payment method is a useful propensity signal.

---

## 6) Contract Clusters, Tenure & Support
![Contract × Tenure × Support](images/Contract_Tenure_Scatter.png)

**Narrative**  
The scatter splits into two worlds: **Monthly = short tenure + high churn**, **Yearly = long tenure + low churn**. Payment only fine-tunes risk inside those clusters. Support tiles show calls are **sparse on average** (~0.92 per customer), so the overall hazard isn’t about frequent contacts—it’s the **small, high-call tail** that’s extremely risky.

**TL;DR:** Two populations—young M2M vs mature yearly; support matters at the tail, but contract sets the lane.

---

## 7) Charges × Usage × the “Unlimited” Promise
![Charges × Usage × Unlimited](images/Charges_Unlimited_Usage.png)

**Narrative**  
The biggest bill shock is **international** (avg ~33.6) not data (~3.4). That’s why Unlimited disappoints **light users**: they pay the premium and still face international fees, so the promise feels hollow. Mid-usage (5–10GB) is the peak-risk band for both plan types; heavy users settle as value becomes obvious.

**TL;DR:** Bill shock is mostly international; Unlimited leaks where usage is low/mid, not high.

---

## 8) State Hotspots, Charges & Support Friction
![Geo × Charges × Support](images/State_Support_Charges.png)

**Narrative**  
Across states, churners average **~2–3** support calls while non-churners sit at **~0.3–0.6**—a **4–8×** gap that’s consistent everywhere. Combine that with outsized **international fees** and you get the red bubbles: states with a higher mix of **intl-active + repeat-contact** customers. The map reflects **mix and experience**, not a simple geographic penalty.

**TL;DR:** Red states are where intl bill shock and repeat contacts cluster; the caller vs non-caller churn gap is huge and universal.

---

## ✅ Recommendations (crisp & prioritized)

1) **Shift the contract mix (highest impact)** — Nudge M2M to annual at upgrade/billing moments with bundle-based incentives; contract choice sets the ceiling on risk.  
2) **Grow households, not lines** — Convert solos to groups; churn collapses and household LTV rises.  
3) **Fix the 5–10GB “no-man’s land”** — Add a mid-tier/rollover or auto-step-up to remove overage pain without overpaying.  
4) **Right-size Unlimited** — Identify **Unlimited <5GB** and offer friendly right-size paths to restore perceived fairness.  
5) **Kill international bill shock** — Travel passes/caps, pre-travel texts, in-bill alerts, simple rules at signup.  
6) **Triage repeat-contact customers** — Auto-route ≥3-call accounts to a save queue; track save rate.  
7) **Onboard like it matters (first 90 days)** — Welcome sequence, bill preview, device/plan setup; senior-friendly concierge.  
8) **Payment hygiene** — Incentivize card autopay; payment behaves as a stickiness proxy.  
9) **Compete where it counts** — Localized competitor-parity bundles in hotspot states; mirror rival offer + device positioning.  
10) **Coach the “moment of truth”** — Empathy + first-contact resolution; QA tone/ownership; small discretionary make-goods.

---

## 📏 Metrics to Track
- Churn %% overall and by **contract, group size, usage band, intl-active**.  
- **Contract mix** (M2M→annual/two-year), **group penetration** (solo→group).  
- **Unlimited mismatch rate** (% Unlimited users <5GB).  
- **Intl fee incidence & average** (alerts sent, passes adopted, credits used).  
- **High-call cohort size & save rate** (≥3 calls).  
- **First-90-day churn**, **time-to-first-contact**.  
- **Payment mix shift** (% on card autopay).  
- **Support QA** (FCR, CSAT/NPS on save calls).

---

### TL;DR (one line)
Cut churn by changing **structure and predictability**: move **M2M → annual**, **solo → group**, **Unlimited-light → right-sized**, and **surprise intl fees → capped & transparent**—while catching **repeat callers** fast and making **support moments excellent**.
Cut churn by changing **structure and predictability**: move **M2M → annual**, **solo → group**, **Unlimited-light → right-sized**, and **surprise intl fees → capped & transparent**—while catching **repeat callers** fast and making **support moments excellent**.
