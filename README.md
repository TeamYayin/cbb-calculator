# 💳 Credit Card Cashback Calculator Assignment

The aim of this project is to design a tool to **calculate cashback** for different credit cards based on transaction category, percentage rewards, and **monthly capping rules**. It also generates a **summary dashboard** of spend distribution by category. 

---

## 📌 Problem Statement

Design a program that accepts:

* A **list of credit card rules** including cashback percentages and caps per category.
* A **CSV file of user transactions** that contains:

  * `Date`
  * `Amount`
  * `Transaction Type` (e.g., Airtel Recharge, Utility, Zomato, EMI, Others)

The system should compute:

* Cashback for each transaction according to the card’s rules.
* Capping for each cashback category.
* Total monthly cashback.
* A **visual breakdown (dashboard)** of total spends by category.

The system should support for multiple cards with different rules, User when uploading file should be prompted to select card variant. 

---

## 📝 Sample Card Cashback Rule (Airtel Axis Card)

| Category                         | Cashback | Monthly Cap  |
| -------------------------------- | -------- | ------------ |
| Airtel Recharge/DTH (Thanks App) | 25%      | ₹250         |
| Utility Bills via Thanks App     | 10%      | ₹250         |
| Swiggy, Zomato, BigBasket        | 10%      | ₹500 total   |
| All Other Spends (non-EMI)       | 1%       | Unlimited    |
| EMI Transactions                 | ❌        | Not Eligible |

> ⚠️ Cashback not applicable to ineligible categories like EMI or excluded merchant types.

---

## 🧮 Cashback Example

### Input:

| Category        | Amount                            |
| --------------- | --------------------------------- |
| Airtel Recharge | ₹2,500                            |
| Utility Bills   | ₹2,500                            |
| Zomato, etc.    | ₹5,000                            |
| Other Spends    | ₹20,000 (₹10,000 of which is EMI) |

### Calculation:

| Category           | Cashback % | Cap  | Cashback Earned |
| ------------------ | ---------- | ---- | --------------- |
| Airtel Recharge    | 25%        | ₹250 | ₹625 → ₹250     |
| Utility Bills      | 10%        | ₹250 | ₹250            |
| Zomato/BigBasket   | 10%        | ₹500 | ₹500            |
| Other Spends (10k) | 1%         | ∞    | ₹100            |

**✅ Total Cashback: ₹1,100**

---

## 📂 CSV File Format

**Input CSV (e.g., `transactions.csv`):**

| Date       | Amount | Transaction Type |
| ---------- | ------ | ---------------- |
| 2024-05-01 | 2500   | Airtel Recharge  |
| 2024-05-02 | 2500   | Utility Bill     |
| 2024-05-03 | 5000   | Swiggy           |
| 2024-05-05 | 10000  | EMI Purchase     |
| 2024-05-07 | 10000  | Grocery          |

---

## ✅ Expected Output

1. **Total Cashback** displayed on screen.
2. **Spend dashboard** (e.g., bar chart/pie chart) of categorized transaction spend.
3. Optional: Export to Excel/CSV with cashback per row.

---

## 📦 How to Run

1. Fork the repo
2. Clone the repo
   `git clone https://github.com/your-org/cashback-calculator.git`
3. Add your script and update the read me to include run instructions like  `python cashback_calculator.py transactions.csv`
4. Please include a dependencies file, such as package.json or requirements.txt, without this, your submission would be considered invalid
5. We will monitor your commits also while evaluating
---

## 🚀 Extension Ideas

* UI with Streamlit or Flask
* Import rules from JSON or YAML

---

