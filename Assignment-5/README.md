
# 🧠 RM Assist – Relationship Manager AI Assistant

**RM Assist** is a smart assistant built using Python and OpenAI to help Relationship Managers (RMs) make better, faster, more informed decisions when interacting with customers. It simulates a CRM overlay experience with intelligent customer summaries, engagement analysis, recommended actions, and ready-to-use scripts — all in your terminal.

---

## 🔥 Initial User Prompt

> My idea is as follows:  
> "RM Assist" – Relationship Manager (RM) AI Assistant  
> 👉 For internal bank teams (RMs / Sales teams)  
>
> Chrome plugin overlays on the bank’s CRM or internal systems.  
> Summarizes key insights about a customer (balance trends, product holdings, cross-sell/upsell opportunities) in simple language.  
> Auto-suggests the next best action (NBA): "This customer’s balance dropped 20% in 3 months; suggest FD renewal or FX offers."  
> Can generate call scripts or email drafts personalized to the customer.  
>
> 🔧 Use case: RM opens CRM, clicks plugin → summary + action plan + draft email populated instantly.

---

## 🧪 Prompt Evaluation & Evolution (By ChatGPT)

| Criteria                       | Status Initially | Enhanced By ChatGPT |
|-------------------------------|------------------|----------------------|
| Explicit Reasoning Instructions | ❌ No            | ✅ Yes (step-by-step prompts) |
| Structured Output Format      | ❌ No             | ✅ Yes (Panels + JSON/call style) |
| Tool Separation (Reason vs Action) | ❌ No        | ✅ Yes (functions used distinctly) |
| Instructional Framing         | ❌ No             | ✅ Sample formats provided |
| Internal Self-Checks          | ❌ None           | ✅ Added basic validation |
| Conversation Loop             | ❌ One shot only  | ✅ Multi-turn with continue/exit |
| Reasoning Type Tagging        | ❌ No             | ✅ Customer type tagging |
| Error Handling                | ❌ Missing        | ✅ UTF-8 + fallback scripts |
| PDF/CSV Export                | ❌ None           | ✅ Implemented and validated |

---

## ✅ Final Tests Passed

| Test Case | Result | Notes |
|-----------|--------|-------|
| Multi-customer picker | ✅ Pass | CLI simulation of CRM |
| Balance chart rendering | ✅ Pass | ASCII + AED |
| NBA logic (drop vs rise) | ✅ Pass | FX/FD recommendation |
| Script generation | ✅ Pass | Call + email with employer |
| CSV Export | ✅ Pass | UTF-8 validated |
| PDF Generation | ✅ Pass | Works using fpdf2 |
| Encoding safety | ✅ Pass | Replaced or skipped emojis for PDF |
| Loop navigation | ✅ Pass | Continue or exit RM console |
| Type classification | ✅ Pass | Saver, Premium, At Risk, etc. |
| Analytics dashboard | ✅ Pass | Count + average risk score |

---

## 🧩 Functions & Modules

### 🔹 `summarize_customer(data)`
Prints a customer summary with employer, industry, net worth, activity, and holdings.

### 🔹 `engagement_score(data)`
Scores each customer out of 100 based on holdings, activity, and balance trend.

### 🔹 `customer_type(data)`
Classifies customer as:
- 📉 At Risk
- 🧍 Passive Saver
- 💼 Premium Growth
- 🎯 Spender
- 🧠 Unclassified

### 🔹 `recommend_nba(data)`
Generates a Next Best Action based on the balance trend.

### 🔹 `generate_scripts(data)`
Returns a call script and email template using customer details.

### 🔹 `show_balance_chart(data)`
Displays last 3-months balance with bars and AED values.

### 🔹 `rm_todo_list()`
Checklist for the RM: call today, suggest FD/FX, log in CRM.

### 🔹 `get_follow_up_date()`
Returns a smart follow-up date (3 working days ahead).

### 🔹 `generate_pdf_summary(...)`
Creates a PDF with all details for uploading/emailing to CRM.

### 🔹 `show_analytics(customers)`
Shows customer type breakdown and average risk score.

---

## 🖼️ Screenshots

### 🔸 Customer Profile
```
👤 Ali
🏢 Emirates Airlines | Industry: Aviation
💰 Max Net Worth: AED 150000
📊 Balance Trend: drop
📦 Products: Savings Account, Fixed Deposit
📣 Campaign History: Offered FX in Jan; no response
```

### 🔸 Engagement Score
```
📈 Score: 45/100 - ⚠️ At Risk
```

### 🔸 Balance Trend
```
Jan: ████████████ (AED 98000)
Feb: ███████      (AED 58000)
Mar: ███          (AED 30000)
```

### 🔸 RM To-Do List
```
✔ Review customer in CRM
✔ Offer relevant FD/FX pitch
✔ Call before EOD
✔ Schedule follow-up in 3 days
✔ Mark customer as 'At Risk' if applicable
```

---

## 🚀 How to Run This Project

1. Clone or unzip this repo
2. Run:
```bash
pip install rich fpdf2
cd rm_assist_plugin_ultimate
python rm_main.py
```
3. Select customers, explore their details, and export results as CSV or PDF

---

## 👨‍💼 Made For

- RM Simulations
- Fintech UX Prototyping
- AI-powered CRM Overlays
- Use in Interviews / Demos / Presentations

---

Built with ❤️ by combining ChatGPT, Python, fpdf2, and CLI magic.
