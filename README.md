# 🛒 E-commerce Order Processing Workflow (n8n)

An automated **E-commerce Order Processing** workflow built using **n8n**. This workflow reads customer orders from Google Sheets, identifies premium orders based on the order amount, stores premium orders in a separate spreadsheet, and generates a sales summary for reporting.

---

## 📌 Overview

This workflow automates the order processing pipeline by:

- Reading order data from Google Sheets.
- Classifying orders as **Premium** or **Normal**.
- Saving premium orders into a separate Google Sheet.
- Calculating sales statistics.
- Sending a summary report via Gmail or Slack.

This project demonstrates how to automate business workflows and generate reports using n8n.

---

## 🚀 Workflow

```text
Google Sheets Trigger
        │
        ▼
Get Rows from Google Sheets
        │
        ▼
       IF Node
(Order Amount > ₹10,000?)
    ┌──────────────┐
    │              │
    ▼              ▼
 Premium        Normal
    │
    ▼
Append Premium Orders
to Google Sheet
    │
    ▼
Summarize
    │
    ▼
Gmail / Slack
```

---

## 🛠 Nodes Used

| Node | Purpose |
|------|---------|
| Google Sheets Trigger | Detects new or updated orders |
| Google Sheets (Read Rows) | Reads all order records |
| IF | Classifies Premium and Normal orders |
| Google Sheets (Append Row) | Stores Premium Orders |
| Summarize | Calculates sales statistics |
| Gmail / Slack | Sends daily sales summary |

---

## 📊 Business Logic

### Premium Order

An order is considered **Premium** when:

```text
Order Amount > ₹10,000
```

Otherwise, it is classified as a **Normal Order**.

---

## 📥 Input Data

Example Order

| Order ID | Customer | Product | Order Amount | City |
|----------|----------|---------|-------------:|------|
| ORD001 | Rahul | Laptop | ₹65,000 | Hyderabad |

---

## 📈 Output

### Premium Orders Sheet

All premium orders are automatically appended to a separate Google Sheet.

Example:

| Order ID | Customer | Product | Order Amount |
|----------|----------|---------|-------------:|
| ORD001 | Rahul | Laptop | ₹65,000 |
| ORD005 | Kiran | Smartphone | ₹28,000 |

---

## 📊 Sales Summary

The workflow calculates:

- Total Premium Orders
- Total Premium Sales
- Average Premium Order Value
- Highest Order Amount
- Lowest Order Amount

Example Output

| Metric | Value |
|--------|-------:|
| Premium Orders | 27 |
| Total Premium Sales | ₹8,37,700 |
| Average Order Value | ₹31,026 |
| Highest Order | ₹95,000 |
| Lowest Premium Order | ₹11,000 |

---

## 📧 Notification

After processing, the workflow sends a summary through **Gmail** or **Slack**.

Example Message

```text
📦 Daily Premium Order Summary

Total Premium Orders : 27

Total Premium Sales : ₹8,37,700

Average Order Value : ₹31,026

Highest Order : ₹95,000

Lowest Premium Order : ₹11,000

Workflow completed successfully ✅
```

---

## 💡 Concepts Practiced

This workflow demonstrates:

- Google Sheets Integration
- Conditional Logic (IF)
- Data Filtering
- Data Summarization
- Automated Reporting
- Workflow Automation
- Business Process Automation

---

## 🎯 Learning Objectives

After building this workflow, you'll learn how to:

- Read data from Google Sheets
- Filter records using conditions
- Route workflow branches
- Store processed data
- Generate business reports
- Send automated notifications
- Build real-world automation workflows

---

## 📸 Workflow Screenshot


## workflow design

![image alt](https://github.com/n8n-workflows-projects/E-commerce-Order-Processing/blob/d5fdcb6dd5f5a4ea4703421b9854cdd82a987941/Screenshot%202026-07-08%20112453.png)

## workflow output

![image alt]()
---

## 📂 Project Structure

```
ecommerce-order-processing/
│
├── README.md
├── workflow.json
├── images/
│   ├── workflow.png
│   └── output.png
└── sample-data/
    └── ecommerce-orders.csv
```

---

## 🧰 Requirements

- n8n
- Google Sheets API Credentials
- Gmail Credentials (optional)
- Slack Credentials (optional)
- Google Spreadsheet

---

## 📚 Skills Covered

- n8n
- Google Sheets
- Conditional Logic
- Business Automation
- Data Processing
- Reporting
- Sales Analytics
- Workflow Design

---

## ⭐ Future Improvements

- Store Normal Orders in a separate sheet
- Generate PDF Sales Reports
- Daily Scheduled Execution
- Send reports to multiple recipients
- Add charts and dashboards
- Integrate with CRM systems
- Create monthly sales analytics
- Add AI-generated sales insights

---

## 📄 License

This project is open-source and intended for learning, experimentation, and personal use.
