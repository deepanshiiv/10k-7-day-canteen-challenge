# 🚨 The ₹10K / 7-Day Canteen Challenge

> Build the smartest college canteen possible with exactly ₹10,000, only 7 days, and ~200 potential students per day.

## 🎯 Mission

You are the brain behind a next-generation college canteen startup.

You have:

- 💰 Exactly ₹10,000
- 📅 Only 7 days
- 👨‍🎓 ~200 potential customers per day
- 🍔 One college canteen

Your mission is to turn this ₹10,000 into the smartest, most student-friendly, low-waste and profitable 7-day canteen operation possible.

### 🚨 Critical Budget Rule

₹10,000 is the **TOTAL budget for all 7 days**.

It does **NOT** reset every day.

It is **NOT** a monthly budget.

The operation must **never exceed ₹10,000 at any point**.

---

## Required Answer Format and Assumptions

Return concise Markdown using these sections in order:

1. **Assumptions and decision summary:** State unknowns, label estimates, explain the budget interpretation, and give the strategy in 3–5 bullets.
2. **Menu and unit economics:** Table with item, category, unit food cost, selling price, contribution per serving, day-one demand, and maximum stock.
3. **Seven-day operating plan:** One row per day with theme, items and planned quantities, expected buyers, estimated revenue, planned food spend, cumulative spend, remaining budget, and learning/marketing action. Item quantities and costs must reconcile to spend.
4. **Demand update example:** Show one item's sales, sell-through, factor, rounded stock recommendation, and any cap applied.
5. **Daily close and dashboard:** Give a reusable record for units sold, revenue, food cost, gross profit, waste, top/weak item, peak hour, average order value, repeat customers (if measurable), feedback, and next-day stock.
6. **Seven-day financial summary:** Recalculate projected buyers, revenue, food cost, gross profit, purchases, and remaining budget from the plan. List excluded operating costs.
7. **Risks and next actions:** Identify facts to verify before purchasing or serving.

Use the given figures as illustrative planning assumptions, not verified local facts. Do not invent supplier quotes, actual sales, survey results, or local legal requirements. If information is missing, state a conservative assumption and show how new data would change the plan. Flag allergens and food-safety or licensing requirements for local verification.

---

# Optional Context Slots

Use supplied values when present; otherwise retain the defaults and label assumptions. These inputs can refine estimates but cannot override the ₹10,000 total cap or the seven-day duration.

- Local supplier quotes: `{{LOCAL_SUPPLIER_QUOTES | optional}}`
- Equipment and staffing available: `{{AVAILABLE_RESOURCES | optional}}`
- Dietary, allergen, or menu restrictions: `{{FOOD_RESTRICTIONS | optional}}`
- Actual sales data for prior days: `{{SALES_HISTORY | none on day one}}`
- Operating dates or hours: `{{OPERATING_SCHEDULE | seven consecutive days}}`

---

# 🍔 1. Smart Menu System

Create **8–12 affordable and realistic items**.

The menu should contain:

- 🍟 Quick snacks
- 🍚 Filling meals
- 🥤 Beverages
- 🥗 Vegetarian options
- 🔥 1–2 student-craze items

For every item calculate:

| Item | Category | Cost | Selling Price | Profit | Expected Demand | Maximum Stock |
|---|---|---:|---:|---:|---:|---:|
| Masala Maggi | Snack | ₹22 | ₹40 | ₹18 | 30 | 35 |
| Veg Grilled Sandwich | Snack | ₹28 | ₹50 | ₹22 | 25 | 30 |
| Aloo Frankie | Meal | ₹25 | ₹45 | ₹20 | 25 | 30 |
| Veg Fried Rice | Meal | ₹35 | ₹60 | ₹25 | 25 | 30 |
| Aloo Paratha + Curd | Meal | ₹32 | ₹55 | ₹23 | 20 | 25 |
| Masala Fries | Snack | ₹20 | ₹40 | ₹20 | 25 | 30 |
| Veg Momos | Student Craze | ₹25 | ₹50 | ₹25 | 35 | 40 |
| Peri-Peri Momos | Student Craze | ₹30 | ₹60 | ₹30 | 30 | 35 |
| Lemon Iced Tea | Beverage | ₹10 | ₹25 | ₹15 | 35 | 40 |
| Cold Coffee | Beverage | ₹18 | ₹40 | ₹22 | 30 | 35 |
| Nimbu Shikanji | Beverage | ₹8 | ₹20 | ₹12 | 30 | 35 |

### Rule

**Maximum stock is NOT mandatory stock.**

Stock should change according to predicted demand.

---

# ⚡ 2. Demand Prediction Engine

The canteen should learn from daily sales.

Use the following method for each item after day one:

```text
Sell-through = Units Sold / Units Stocked
Recommended Stock = ceiling(Previous Comparable-Day Sales × Demand Factor)
```

Example:

If Monday sells:

```text
24 plates of Momos
```

and the predicted demand factor for Tuesday is:

```text
1.2
```

Then:

```text
24 × 1.2 = 28.8 ≈ 29 plates
```

So Tuesday's recommended stock becomes **29 plates**.

### Stock Rules

- If an item sells out, use a demand factor of **1.20**.
- Otherwise, sell-through of **80% or more** uses **1.15**.
- Sell-through of **50% to less than 80%** uses **1.00**.
- Sell-through **below 50%** uses **0.75**.
- Round servings up to a whole unit. Cap recommended stock at the item's maximum and at the quantity affordable within the remaining total budget. If the budget cap reduces a recommendation, state the trade-off.
- If sales data is missing, do not interpret it as zero demand; retain a conservative baseline and label the assumption. For a new item, use a comparable item and identify it.
- Unsold stock is not automatically waste if it can be safely carried forward. Record actual discarded quantity and cost separately.

The goal is to avoid both:

- ❌ Stockouts
- ❌ Food wastage

---

# 📅 3. Seven-Day Experience

Use these identities as guidance, not mandatory full menus. Adjust selections using sales and feedback.

| Day | Identity | Menu and operating action |
|---|---|---|
| Monday | Back-to-Campus Fuel | Familiar comfort food; establish baseline demand. Hero combo: Maggi + Lemon Iced Tea, ₹55. |
| Tuesday | Combo Attack | Test Frankie + Shikanji ₹60, Sandwich + Iced Tea ₹65, or Maggi + Iced Tea ₹55; avoid deep discounts. |
| Wednesday | Midweek Madness | Test a small menu; optional Peri-Peri Momo drop capped at 35 plates. |
| Thursday | Student Favourite Takeover | Use three days of sales and student votes to choose hero items; ask “What should stay on the menu?” |
| Friday | Chill & Feast | Feature popular items. Optional spin per ₹100 spent; cap reward cost and prefer low-cost add-ons. |
| Saturday | Desi Twist | Feature Aloo Paratha, Aloo Frankie, Fried Rice, Shikanji, or Iced Tea; share ingredients where practical. Frankie + Shikanji combo: ₹60. |
| Sunday | Grand Finale | Use all seven days of evidence to choose the final menu and a potential signature item; do not simply repeat Monday. |

---

# 💰 4. The ₹10,000 Money Game

The budget is ONE shared wallet.

## Starting Budget

**₹10,000**

### 7-Day Spending Plan

| Day | Spending | Remaining Budget |
|---|---:|---:|
| Monday | ₹1,300 | ₹8,700 |
| Tuesday | ₹1,350 | ₹7,350 |
| Wednesday | ₹1,450 | ₹5,900 |
| Thursday | ₹1,400 | ₹4,500 |
| Friday | ₹1,550 | ₹2,950 |
| Saturday | ₹1,400 | ₹1,550 |
| Sunday | ₹1,550 | ₹0 |
| **TOTAL** | **₹10,000** | **₹0** |

### 🚨 Hard Rule

```text
Total spending ≤ ₹10,000
```

Never exceed the total cumulative food-purchase budget. The daily amounts above are planning ceilings, not mandatory spend; unused budget carries forward. For this challenge, count the unit food cost of every portion stocked/prepared as that day's spend, including unsold portions. Do not treat sales revenue as additional purchasing cash.

Report revenue, food cost of sold portions, gross profit, total planned purchase spend, and waste cost separately. Gross profit is revenue minus food cost of portions sold; it is not net profit. Do not count wages, rent, electricity, tax, packaging, or equipment unless values are provided, and list these as exclusions. Reconcile every total to the item quantities in the seven-day plan.

---

# 📈 5. Expected Sales Model

Assume approximately **200 potential students per day**.

| Day | Expected Buyers | Average Spend | Expected Revenue |
|---|---:|---:|---:|
| Monday | 120 | ₹42 | ₹5,040 |
| Tuesday | 135 | ₹45 | ₹6,075 |
| Wednesday | 150 | ₹45 | ₹6,750 |
| Thursday | 155 | ₹47 | ₹7,285 |
| Friday | 170 | ₹50 | ₹8,500 |
| Saturday | 145 | ₹45 | ₹6,525 |
| Sunday | 175 | ₹50 | ₹8,750 |
| **TOTAL** | **1,050** | — | **₹48,925** |

### Planned Inventory Budget

**₹10,000**

### Simplified Cash Surplus After Planned Purchases

```text
₹48,925 - ₹10,000 = ₹38,925
```

This is projected revenue minus planned purchases, not gross profit or net profit. Recalculate it if the operating plan changes.

> **Note:** This is a simplified challenge model. Real-world profit would also need to account for staff wages, rent, electricity, equipment, taxes, packaging, spoilage and other operating expenses.

---

## Daily Learning and Student Engagement

At close, record orders, sales, costs, gross profit, actual waste, top/weak item, peak hour, average order value, and repeat customers when measurable. Classify each item as **Scale**, **Keep**, or **Pause** using demand, contribution, and waste; the menu may change daily. Collect quick student ratings for taste, price, speed, and likelihood to repurchase, plus one suggestion for tomorrow. Use sales and feedback together.

Use brief student-facing campaign copy where useful, such as “Monday isn't ready for this Maggi,” “35 plates. That's it,” “Friday called. It wants momos,” or “You voted. We cooked.” Keep promotions within the budget and the output schema.
