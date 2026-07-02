# Copilot in Excel — Participant Exercise Guide
### Formulas & Pivot Tables for the Project Management Office (PMO)
**Bajaj Finance Limited | M365 Copilot Training**
**File:** `BFL_PMO_Copilot_Demo.xlsx`

---

## Before You Begin

- Use **Copilot agent** to open the agent in the Copilot panel
- Add `BFL_PMO_Copilot_Demo.xlsx` from OneDrive
- Keep the Copilot panel open throughout all exercises
- The file has **25 rows of PMO delivery-tracker data** — one sheet, no formula columns yet
- Columns N–Q are intentionally blank — you will fill these using Copilot

### Dataset Overview

Each row is a **tracked work item** on the PMO delivery board — a deliverable, milestone, change request, risk, or dependency that a Project Manager is driving to closure across a portfolio.

| Column | Field | Description |
|--------|-------|-------------|
| A | Item ID | Unique work-item reference (PMO-001 to PMO-025) |
| B | Portfolio | Delivery programme the item belongs to |
| C | Portfolio Code | Short portfolio identifier |
| D | Region | West / Central |
| E | Work Item Type | Milestone, Change Request, Deliverable, Dependency, Risk |
| F | Project Manager | PM owning the work item |
| G | Raised Date | When the item was logged on the board |
| H | Closed Date | When it was closed (blank if still open) |
| I | Actual Days | Actual days taken to close the item |
| J | Planned Days (SLA) | Baseline / committed days for that item type |
| K | Project Tier | Tier 1 (highest governance) to Tier 5 |
| L | Priority | Normal, High, Urgent |
| M | Status | Completed, In Progress, Escalated |
| **N–Q** | *(blank)* | **You will add these using Copilot** |

---

## Exercise 1 — Add a Formula Column: Escalation Flag

### Your Turn
Type into the Copilot panel:

```
In column N, add a formula that flags each work item as "Escalate" or
"OK" based on its Priority and Status:
- "Escalate" if Priority is "Urgent" OR Status is "Escalated"
- "OK" for all other cases
Label the column "Escalation Flag". Apply to all 25 rows.
```

### What Copilot Will Produce
```excel
=IF(OR(L3="Urgent",M3="Escalated"),"Escalate","OK")
```
Copilot will name the column, write the formula, and fill it down to N27.

> **Discussion Point:** Which work item types cluster around an Urgent priority or an Escalated status? What does that tell the PMO about where steering-committee attention is really being spent?

---

## Exercise 2 — Add a Formula Column: Schedule Breach

### Your Turn
Type into the Copilot panel:

```
In column O, add a formula that checks whether each work item breached
its committed schedule. Compare the Actual Days in column I against the
Planned Days (SLA) in column J. If Actual Days is greater than Planned
Days, return "Breach". Otherwise return "On Time". If Actual Days is
blank (item still open), return "In Progress".
Label the column "Schedule Breach". Apply to all 25 rows.
```

### What Copilot Will Produce
```excel
=IF(I3="","In Progress",IF(I3>J3,"Breach","On Time"))
```

> **Discussion Point:** Change Requests show the most schedule breaches by a wide margin. What upstream governance gaps — scope control, impact assessment, approval lead time — tend to drive that pattern?

---

## Exercise 3 — Add a Formula Column: Days Open

### Your Turn
Type into the Copilot panel:

```
In column P, calculate the number of days each work item has been open.
If the item is already closed (column H has a date), return 0. If it is
still open, return the number of days since it was raised (column G) up
to today.
Label the column "Days Open". Apply to all 25 rows.
```

### What Copilot Will Produce
```excel
=IF(H3<>"",0,TODAY()-DATEVALUE(G3))
```
Closed items show 0. Open items show how many days they have been sitting on the board.

> **Discussion Point:** Which open items are ageing the most? Are the stale items concentrated under a particular PM, portfolio, or item type — and are any of them Risks or Dependencies that could block downstream milestones?

---

## Exercise 4 — Add a Formula Column: Variance Category

### Your Turn
Type into the Copilot panel:

```
In column Q, classify each closed work item into a schedule-variance
category based on how the Actual Days (column I) compares to the Planned
Days (column J):
- "Fast" if Actual Days is 50% or less of Planned Days
- "Within Plan" if Actual Days is within Planned Days
- "Moderate Overrun" if Actual Days exceeds plan by up to 50%
- "Critical Overrun" if Actual Days exceeds plan by more than 50%
- "In Progress" if Actual Days is blank
Label the column "Variance Category". Apply to all 25 rows.
```

### What Copilot Will Produce
```excel
=IF(I3="","In Progress",IF(I3<=J3*0.5,"Fast",IF(I3<=J3,"Within Plan",IF(I3<=J3*1.5,"Moderate Overrun","Critical Overrun"))))
```

---

## Exercise 5 — Ask Copilot to Explain a Formula

### Your Turn
Copy the formula from cell **Q3** and paste it into the Copilot panel:

```
Explain this formula to me in simple terms. What does each part do?
```

### What Copilot Will Explain
> *"This formula first checks if the Actual Days in I3 is blank — if so, the item is still In Progress. Then it checks if Actual Days is at most half the plan, which means the PM delivered it very Fast. Next it checks if Actual Days is within the full Planned Days — that's Within Plan. If it went over the plan but not by more than 50%, it's a Moderate Overrun. Anything beyond 150% of the plan is a Critical Overrun. Each IF only runs when the previous condition wasn't true."*

---

## Exercise 6 — Create a Pivot Table: Work Items by Type and Status

### Your Turn
Type into the Copilot panel:

```
Create a pivot table that shows the count of work items for each Work
Item Type, broken down by Status (Completed, In Progress, Escalated).
I want to see which work item types have the most unresolved or
escalated cases.
```

### What Copilot Will Produce
A new sheet with a Pivot Table:
- **Rows:** Work Item Type (Milestone, Change Request, Deliverable, Dependency, Risk)
- **Columns:** Status (Completed, In Progress, Escalated)
- **Values:** Count of Item ID

> **Discussion Point:** Risks carry a high escalated-plus-open ratio relative to their volume (only 1 of 4 closed). What does that signal about how actively risks are being worked down versus simply logged and parked?

---

## Exercise 7 — Create a Pivot Table: Average Duration by Project Manager

### Your Turn
Type into the Copilot panel:

```
Now create a pivot table showing the average Actual Days for each
Project Manager, broken down by Work Item Type. I want to identify which
PMs or item types are taking the longest to close.
```

### What Copilot Will Produce
- **Rows:** Project Manager (Pooja Nair, Rahul Sharma, Anita Desai, Vikram Joshi, Ravi Kumar)
- **Columns:** Work Item Type
- **Values:** Average of Actual Days

> **Discussion Point:** Anita Desai carries the highest overall average duration (9.5 days), driven by a single Change Request that ran to 16 days. Is that a capacity problem, a complexity problem, or a scope-control problem — and which item type consistently overruns across multiple PMs?

---

## Exercise 8 — Bonus: Ask Copilot for Insights

### Your Turn
Type into the Copilot panel:

```
Look at the data in this sheet. Which portfolios have the most schedule
breaches? Summarise the key delivery-risk areas for the PMO in 3 bullet
points.
```

### What to Expect
Copilot will scan the data and generate a natural-language summary — no formula needed. This shows how Copilot moves from *calculation* to *analysis* to *insight* within the same Excel session.

---

## Reference: What Your Pivots Should Show

Once you've built the pivots in Exercises 6–7, sanity-check them against these figures:

- **25 work items total** — 18 Completed, 5 In Progress, 2 Escalated
- **Change Requests** are the highest-volume type (7) and the largest source of schedule breaches (6 of 10 total breaches)
- **Risks** show the weakest closure profile — only 1 of 4 closed, the rest open or escalated
- **10 schedule breaches** in total: 8 in West, 2 in Central

*(Trainers: the full pre-built pivot answer key is available separately, so the participant file stays clean for the exercises.)*

---

*Bajaj Finance Limited | AI Academy — Project Management Office | Microsoft Copilot Training Programme*
