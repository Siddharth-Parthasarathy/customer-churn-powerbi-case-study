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

## 🔑 Executive Insights
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
6) **Age & Household effect** — churn rate and customer volume by age
7) **Contract Clusters, Tenure & Support** — scatter of tenure vs churn by contract; support volume.  
8) **Charges × Usage × “Unlimited”** — international vs data charges and usage-plan fit.  
9) **State Hotspots, Charges & Support** — where intl fees and repeat contacts cluster.

> The analysis below follows the same order.

---

## 1) Overview & Churn Reasons
![Overview & Churn Reasons](Images/Overview.png)

**Narrative**  
What jumps out isn’t just the churn level—it’s the shape of churn. The age curve tells a clear story: as customers get older, the likelihood of leaving climbs steadily, even though there are fewer customers in the highest age bands. That means the visible losses in your dashboards are mostly happening in the 30–60 range (because that’s where the people are), but the risk per person quietly spikes after ~60. Two different problems to solve: volume churn in mid-life, rate churn in older cohorts.

The “why” is split between external pull and internal push. The top stated reasons cluster around competitive pull (better offers/devices/speeds/data) and experience push (support attitude). That’s a powerful combination: competitors are winning the promise (price/value/device) while we’re losing the moment (how customers feel after an interaction). Notice that “price too high” is not the top villain—price framing and offer packaging seem to matter more than raw price; people leave when a rival makes the choice easy and our service interaction doesn’t convince them to stay.

Senior customers churn much more than under-30s. That likely isn’t just about age; it hints at device upgrade friction, plan complexity, and support experience not being tailored to what seniors need (plain language, setup help, fewer surprises). Meanwhile, the “Don’t know” bucket is big enough to matter—classic sign of passive churn (no single smoking gun, just death by small frictions). Those customers are perfect targets for a fast, low-friction “stay” offer and a concierge-style check-in.

If we translate this into impact: very rough math says the two biggest levers could be sizeable even with modest improvements. If ~a third of churn is competitive and we win back just 10% of those at-risk cases, that’s about 61 customers saved. If we cut service-attitude churn by 30% through coaching/QA and empowered make-goods, that’s another ~59 saves. Directionally, ~120 saves across these two levers alone (back-of-envelope on this page’s mix) is realistic—and that compounds month after month.

---

## 2) Contracts, Groups & Churn
![Contracts & Groups](Images/Contracts_and_Groups.png)

**Narrative**  
This page screams one thing: structure beats demographics.
Two structural choices—contract and group size—explain the churn story far more than who the customer is.

Group size is a retention engine. Solo lines pay the most per month, but they’re the ones leaving. As soon as a customer adds even one extra line, churn collapses into single digits and stays low as the group grows. Yes, ARPU per line softens, but the household LTV jumps because you’re keeping multiple lines for much longer. The playbook here isn’t “discount more,” it’s “get the second line on the account”—once that happens, the exit door practically closes.

Contract choice dwarfs everything else. Month-to-month sits around ~46% churn, yearly around ~7%—and that pattern holds across genders. In other words, who the customer is matters less than what they signed. The donut shows over half the base is still month-to-month, which explains the overall churn level: we’re weighted toward the riskiest contract.

Why people say they leave backs this up. Nearly half of stated churn is “competitor” (offers/devices), while price alone is a minority slice. That’s classic “value packaging” vs. raw cost: rivals make the decision effortless (bundle + device), and our month-to-month solos are easiest to poach.

Translation to impact: If you migrate just 10% of the month-to-month base into 1-year terms, you shift ~341 customers from a ~46% risk to ~11–7%. That’s ~120 fewer churned customers on that move alone—before any group-plan effect.

---

## 3) Usage × Plan (Unlimited vs Non)
![Usage vs Unlimited](Images/Usage_vs_Unlimited.png)

**Narrative**  
This page is about value fit more than raw usage. Two patterns lock together:

Unlimited is carrying the churn mix. ~67% of customers are on Unlimited and they churn at ~32%, roughly double the non-Unlimited rate (~16%). Even before looking at usage, that plan choice alone explains why total churn sits near 27%.

The danger zone is the middle. Across both plan types, 5–10GB users churn the most (~33–35%). It’s the no-man’s land: limited plans risk bill shock from occasional overages, while Unlimited can feel overpriced because usage isn’t high enough to justify the premium. Either way, perceived value is weak.

Light users tell the clearest story. Customers using <5GB churn very low on non-Unlimited (~12–13%) but very high on Unlimited (~35%). That’s classic plan mismatch—paying for capacity you don’t need erodes perceived fairness and invites switching.

Heavy users are not the highest risk. At ≥10GB, churn is a touch lower than the 5–10GB band for both plan types (~28–30%). Once usage is genuinely high, the Unlimited premium feels justified, which steadies churn—even if competitors dangle offers.

Unlimited is likely a proxy for other risks. Given earlier pages (M2M contracts, competitive poaching), Unlimited probably over-indexes on month-to-month and promo-chasing cohorts, amplifying churn independent of usage.

---

## 4) Geography × International Usage
![Churn by State & Intl Usage](Images/Geo_and_International.png)

**Narrative**  
This page ties place and purpose together. The left matrix shows that customers who are internationally active churn at ~34%, versus ~22% for everyone else—a 12-point lift. That’s not just a pricing story; it reads like complexity + unpredictability: roaming rules, add-ons, and charges that are hard to anticipate.

On the map, most states sit in a steady green band, but a handful of outliers light up with higher churn. Those hotspots are where two forces likely overlap:

Competitive intensity (a local carrier with a sharper offer or device program), and

Travel-heavy profiles (more international usage, more chance of confusion or surprise fees).

Put differently: churn is highest where the need for flexible, cross-border usage meets a rival who packages that promise more clearly. Notice how the scatter isn’t just coastal vs inland; it’s pockets—suggesting local competitors and regional network perception matter as much as national pricing.

The pattern also explains why international usage acts like a risk amplifier rather than a universal problem. In most states the baseline stays tame; it’s when the international-active mix is higher and a strong competitor is present that churn spikes. That’s why statewide averages can be misleading—local mix effects drive the red bubbles.

---

## 5) Tenure, Contract & Payment Mix
![Tenure & Contract](Images/Tenure_Contract_Payments.png)

**Narrative**  
The top-left line isn’t just “older customers churn less.” It’s a hazard curve plus survivorship: people most prone to leave exit early, so the population that remains at 12, 24, 36 months is self-selected for stickiness. That’s why risk decays with age even before you change anything—composition shifts as fragile relationships drop out.

Overlaying contract type shows how structure gates risk. The dashed trends tell us the ceiling on churn is set at sign-up: month-to-month never converges to the annual/two-year bands, even late in life. You can “earn down” risk with time, but only inside the lane the contract gives you. The jitter on the month-to-month series (vs the flat two-year floor) hints at anniversary effects and promo cliffs—periodic bumps where a subset re-evaluates and defects.

On the right, payment method is doing double duty as a behavioral proxy. The base skews to Direct Debit (~55%), then Credit Card (~39%), with a small Paper Check (~5–6%) tail. In this dataset, checks carry the highest churn and credit cards the lowest. That’s less about the instrument and more about the customer archetype behind it: paper checks often correlate with lower digital engagement and more friction; credit-card users tend to be overrepresented in self-serve, high-contactability cohorts. So payment isn’t causal, but it’s a useful signal for propensity.

---

### 6) Age & Household Effect
![Age × Group Size](Images/Age_Group_Size.png)

**What the data is really saying**
- **Two churn engines:** mid-life (30–50) drives volume because it’s the largest base; risk per person **spikes after ~60**, reaching ~40–60%.
- **Not just tenure:** filtering by Account Length keeps the late-life slope, so the age effect isn’t only a survivorship artifact.
- **Solo premium vs. household lock-in:** group size **0** has the highest per-line charge **and** the highest churn; at **2+ lines**, churn **drops into single digits** and stays low while per-line charges stabilize.

*TL;DR: mid-life ages create most losses by sheer size; seniors carry the highest personal risk; forming a household flips churn from high to single-digit.*


## 7) Contract Clusters, Tenure & Support
![Contract × Tenure × Support](Images/Contract_Tenure_Scatter.png)

**Narrative**  
The scatter splits into two clean clusters:

On the left, Monthly customers: short average tenure (single-digit to teens, in months) and high churn (roughly 30–60%).

On the right, Yearly customers: longer tenure (mid-30s to ~50 months) and low churn (≈5–10%).

Payment method is present as a slicer, but within each contract cluster the points sit close together—contract category dominates; payment method only fine-tunes risk at the margins.

The support tiles on the left (6,123 total calls; 0.92 calls/customer on average) add an important wrinkle: support contacts are sparse on average, so the overall hazard you see here is not driven by frequent interactions. That fits the broader story: churn is front-loaded (newer, M2M customers) and structural (contract choice), with a fat-tail of high-call customers who are few in number but extremely at risk. In other words, the average hides the tail.

---

## 8) Charges × Usage × the “Unlimited” Promise
![Charges × Usage × Unlimited](Images/Charges_Unlimited_Usage.png)

**Narrative**  
This page explains why “Unlimited” isn’t a cure-all: it solves data overage anxiety, but it doesn’t protect against international charges, which are the real bill-shock driver here.

On the left, the single most telling cue is the scale difference: average extra international charges (~33.6) are an order of magnitude larger than extra data charges (~3.4). In other words, when customers are surprised by their bill, it’s far more likely to be from international activity than from domestic data.

Overlay that with the usage × plan matrix and the picture clicks into place:

Light users (<5GB): they barely use data, yet Unlimited posts very high churn (~35%) while non-Unlimited is low (~12–13%). That’s classic value mismatch—paying a premium and still being exposed to international fees makes the “Unlimited” promise feel hollow.

Mid users (5–10GB): churn peaks for both plan types (~33–35%). It’s the gray zone—too much usage for the cheapest limited plans (risking occasional fees), but not enough to feel the Unlimited premium is worth it. Perceived value is weakest here.

Heavy users (≥10GB): churn eases a bit (high-20s) for both plans. Once usage is genuinely high, the Unlimited price/benefit story finally makes intuitive sense, so dissatisfaction tapers—even though international charges can still sting.

---

## 9) State Hotspots, Charges & Support Friction
![Geo × Charges × Support](Images/State_Support_Charges.png)

**Narrative**  
What looks regional at first glance is actually behavioral once you peel it back.

The map shows a few state hotspots, but the line chart underneath tells you why those bubbles appear: churned customers log 2–3 support calls on average in almost every state, while non-churners hover around ~0.3–0.6. That 4–8× gap is consistent across the map. In other words, churn isn’t a coastal vs. inland story; it’s a “many calls → high risk” story that happens to cluster where there are more of those customers.

The tiles on the left put a price tag on that friction. The typical bill surprise is international, not data (avg extra international charges ≈ 33.6 vs data ≈ 3.4). When you combine unpredictable fees with multiple contact attempts, you get the exact states that light up red: places with a higher mix of internationally active users and spiky support demand.

Notice how flat the non-churner call line is across states. Retained customers look the same everywhere: they rarely call. That’s the systemic signal here—the geography doesn’t change the pattern, it changes the mix (how many international travelers and high-friction cases you have).

Bottom line: the map is a mirror for customer mix and experience, not a map of the network itself. Where international bill shock and repeat contacts concentrate, churn follows.

---

## 🔎 Summary (what’s really driving churn)

Churn is front-loaded: risk is highest in the first months and then decays (survivorship).
Structure beats demographics: Month-to-Month contracts (~46% churn) and solo lines drive losses; yearly/two-year and group plans are naturally sticky.
The value gap is clearest for Unlimited (≈32% churn vs ~16% non-Unlimited) and for 5–10GB users (peak risk): plan–usage mismatch + promo chasing.
International charges (avg ~33.6) dwarf extra data fees (~3.4) → the main “bill shock” culprit.
Support friction is a huge signal: churners average ~2–3 calls vs ~0.3–0.6 for non-churners (4–8× gap).
Geography is mix, not destiny: hotspots are states with more intl-active customers + strong local competitors.
Payment is a proxy: paper check is the riskiest, credit card the safest, direct debit in between.
Seniors churn more (complexity/upgrade friction), while under-30 cohorts are relatively stable.

---

## ✅ Recommendations
1) Shift the contract mix (highest impact)

Who: Month-to-Month customers, especially in first 6–12 months.
What: Targeted nudges to 1-year terms at upgrade/billing moments (bundle-based, not price-only).
Why: Contract sets the ceiling on risk; even at long tenure, M2M never converges to annual churn.

2) Grow households, not lines

Who: Solo accounts.
What: “Add a line” offers (family/partner bundles, small device credits).
Why: The second line collapses churn into single digits; household LTV jumps even if ARPU/line softens.

3) Fix the 5–10GB “no-man’s land”

Who: Users averaging 5–10GB (both plan types).
What: Introduce a mid-tier or rollover/auto-step-up option; simplify message: “never overpay, never overage.”
Why: This band is the peak risk across plans.

4) Right-size Unlimited (stop the mismatch)

Who: Unlimited + <5GB users.
What: Proactive plan right-sizing outreach; make it positive (“save without losing peace of mind”).
Why: Unlimited underperforms badly for light users → perceived unfairness.

5) Kill international bill shock

Who: Intl-active customers and hotspot states.
What: Travel passes/caps, pre-travel texts, in-bill alerts, and post-trip credits rules; make intl fees transparent at signup.
Why: Intl charges are the largest surprise cost and add ~12pp churn lift.

6) Triage repeat-contact customers

Who: ≥3 support calls in 60–90 days.
What: Auto-route to a save queue, empower agents with small make-goods and plan fixes; track save rate.
Why: The callers vs. non-callers churn gap is 4–8× in every state.

7) Onboard like it matters (first 90 days)

Who: All new/M2M signups; concierge lane for seniors.
What: Welcome sequence, bill preview, device/plan setup help, “what to expect” on intl/data.
Why: Most churn happens early; seniors especially need clarity over complexity.

8) Payment method hygiene

Who: Paper check and (where risky) direct-debit cohorts.
What: Incentivize card autopay (rewards, fee waivers); make switching trivial.
Why: Payment is a strong behavioral proxy for stickiness/contactability.

9) Compete where it counts

Who: Hotspot states; M2M + solo + Unlimited-light users.
What: Competitor-parity bundles (offer + device + protection/backup), localized to rival promos.
Why: Stated reasons are dominated by competitor offers/devices—win the promise, not just the price.

10) Coach the “moment of truth”

Who: Frontline support.
What: Train for empathy + first-contact resolution; QA on tone and ownership; small discretionary credits.
Why: “Attitude of support person” is a top reason; one bad call undoes any pricing story.

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

Bottom line: Cut churn by shifting Month-to-Month (M2M) customers to 1-year plans, converting single-line accounts into group plans, right-sizing “Unlimited” for low-usage customers, capping/clearly explaining international fees, and jumping fast on repeat support callers.
