<div align="center">

<img src="https://img.shields.io/badge/🍽️%20Swiggy-Data%20Analysis-FC8019?style=for-the-badge&labelColor=FC8019&color=1C1C1C" alt="Swiggy Data Analysis" height="50"/>

# 🍽️ Swiggy Data Analysis

### *Turning Food Delivery Data into Actionable Intelligence*

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

<br/>

> **100,000+ Users** · **5.2M+ Menu Records** · **6 Relational Tables** · **End-to-End Analytics Pipeline**

</div>

---

## 📌 Table of Contents

- [🧠 Project Overview](#-project-overview)
- [💡 Key Insights](#-key-insights)
- [🗂️ Dataset Schema](#-dataset-schema)
- [⚙️ Project Workflow](#-project-workflow)
- [📊 Power BI Dashboard](#-power-bi-dashboard)
- [🏗️ Repository Structure](#-repository-structure)
- [🛠️ Tech Stack](#-tech-stack)
- [🚀 Getting Started](#-getting-started)
- [👤 Author](#-author)

---

## 🧠 Project Overview

Swiggy is one of India's largest food delivery platforms, serving millions of customers daily across hundreds of cities. This project delivers a **full end-to-end data analytics pipeline** — from raw, messy CSV data all the way to an interactive executive dashboard.

The analysis spans **6 relational tables**, covering the entire ecosystem of food delivery: what customers order, where restaurants are located, what cuisines are offered, and how sales distribute across demographics and geographies.

**Goals:**
- 🧹 Clean and normalize raw Swiggy datasets using **Python & Pandas**
- 🔗 Establish relational integrity across 6 tables
- 📈 Build a rich **Power BI dashboard** to surface business insights
- 🔍 Deliver actionable intelligence on sales, customers, and cuisine trends

---

## 💡 Key Insights

<div align="center">

| 🏆 Insight | 📊 Value |
|---|---|
| 🥗 Vegetarian Sales Revenue | **₹122 Million** |
| 📈 Veg vs Non-Veg Sales Advantage | **+7.2% Higher** |
| 👑 Top 10% Customers Contribution | **80% of Total Sales** |
| 🏙️ Highest Ordering City | **Tirupati — ₹43 Million** |
| 👥 Total Users Analyzed | **100,000+** |
| 📋 Menu Records Processed | **5.2 Million** |

</div>

> 💬 *These insights enable restaurant owners, business analysts, and Swiggy stakeholders to make data-driven decisions around menu curation, regional expansion, and targeted marketing.*

---

## 🗂️ Dataset Schema

The dataset comprises **6 relational tables** designed to capture the full lifecycle of a food delivery order.

<details>
<summary><b>🍲 Food Table</b> — click to expand</summary>

| Column | Type | Description |
|---|---|---|
| `f_id` | INT | Unique food item identifier |
| `item` | VARCHAR | Name of the food item |
| `veg_or_non_veg` | ENUM | Dietary classification (Veg / Non-Veg) |

</details>

<details>
<summary><b>📋 Menu Table</b> — click to expand</summary>

| Column | Type | Description |
|---|---|---|
| `menu_id` | INT | Unique menu entry identifier |
| `r_id` | INT | Foreign key → Restaurant |
| `f_id` | INT | Foreign key → Food |
| `cuisine` | VARCHAR | Type of cuisine |
| `price` | DECIMAL | Item price in INR |

</details>

<details>
<summary><b>📝 Orders Table</b> — click to expand</summary>

| Column | Type | Description |
|---|---|---|
| `order_date` | DATE | Date of the order |
| `sales_qty` | INT | Number of units sold |
| `sales_amount` | DECIMAL | Revenue generated |
| `currency` | VARCHAR | Currency of transaction |
| `user_id` | INT | Foreign key → Users |
| `r_id` | INT | Foreign key → Restaurant |

</details>

<details>
<summary><b>🛍️ Order Type Table</b> — click to expand</summary>

| Column | Type | Description |
|---|---|---|
| `order_id` | INT | Unique order identifier |
| `type` | VARCHAR | Delivery type (e.g., Delivery, Dine-in) |

</details>

<details>
<summary><b>🍴 Restaurant Table</b> — click to expand</summary>

| Column | Type | Description |
|---|---|---|
| `id` | INT | Unique restaurant identifier |
| `name` | VARCHAR | Restaurant name |
| `country` | VARCHAR | Country of operation |
| `city` | VARCHAR | City of operation |
| `rating` | FLOAT | Average customer rating |
| `rating_count` | INT | Number of ratings received |
| `cuisine` | VARCHAR | Primary cuisine type |
| `link` | URL | Swiggy listing URL |
| `address` | TEXT | Full address |

</details>

<details>
<summary><b>👥 Users Table</b> — click to expand</summary>

| Column | Type | Description |
|---|---|---|
| `user_id` | INT | Unique user identifier |
| `name` | VARCHAR | User full name |
| `age` | INT | User age |
| `gender` | VARCHAR | Gender |
| `marital_status` | VARCHAR | Marital status |
| `occupation` | VARCHAR | User occupation |

</details>

---

## ⚙️ Project Workflow

```
Raw CSV Data
     │
     ▼
┌─────────────────────────────────┐
│  🧹 Phase 1 — Data Cleaning     │
│  • Detect & handle null values  │
│  • Remove duplicate records     │
│  • Standardize data types       │
│  • Fix inconsistent entries     │
└────────────┬────────────────────┘
             │
             ▼
┌─────────────────────────────────┐
│  🛠️ Phase 2 — Data Formatting   │
│  • Rename columns for clarity   │
│  • Drop irrelevant columns      │
│  • Remove redundant tables      │
│  • Validate referential keys    │
└────────────┬────────────────────┘
             │
             ▼
┌─────────────────────────────────┐
│  💾 Phase 3 — Data Export       │
│  • Export clean CSVs            │
│  • Store in /Processed Data     │
└────────────┬────────────────────┘
             │
             ▼
┌─────────────────────────────────┐
│  📊 Phase 4 — Power BI          │
│  • Load clean data              │
│  • Power Query transformations  │
│  • Build relational data model  │
│  • Design interactive visuals   │
│  • Publish & share dashboard    │
└─────────────────────────────────┘
```

---

## 📊 Power BI Dashboard

An interactive, executive-grade dashboard was built in **Power BI** to visualize all key metrics.

**Dashboard Features:**
- 📅 **Time-Series Analysis** — Sales trends over time
- 🌍 **Geographic Heatmaps** — City-level order volume
- 🥗 **Veg vs Non-Veg** — Comparative sales breakdown
- 👥 **Customer Segmentation** — Demographics & behavior
- 🏆 **Top Restaurants** — Ranked by revenue & rating
- 📦 **Order Type Distribution** — Delivery vs Dine-in

<div align="center">

[![Open Power BI Dashboard](https://img.shields.io/badge/🚀%20View%20Live%20Dashboard-Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://app.powerbi.com/reportEmbed?reportId=3bc300f1-90fa-4f85-8ccc-c27ae4e3f865&autoAuth=true&ctid=2e589d81-ea7a-4dc7-8fb2-84ba95cc947f)

</div>

---

## 🏗️ Repository Structure

```
📦 Swiggy_Data_analysis/
├── 📓 Swigy.ipynb                  # Full Python analysis notebook
├── 📁 Raw Dataset/                 # Original unprocessed CSV files
├── 📁 Proccesed Data (Python)/     # Cleaned & formatted output files
├── 📁 screenshot Dashboard/        # Power BI dashboard screenshots
└── 📄 README.md                    # Project documentation
```

---

## 🛠️ Tech Stack

<div align="center">

| Layer | Tool | Purpose |
|---|---|---|
| 🐍 Language | Python 3.10+ | Core scripting & analysis |
| 📦 Library | Pandas | Data cleaning & transformation |
| 📓 Environment | Jupyter Notebook | Interactive development |
| 📊 BI Tool | Microsoft Power BI | Visualization & dashboards |
| 🗄️ Data Format | CSV | Raw & processed data storage |

</div>

---

## 🚀 Getting Started

### Prerequisites

Make sure you have Python 3.10+ and Jupyter installed.

```bash
pip install pandas numpy jupyter
```

### Run the Analysis

```bash
# 1. Clone the repository
git clone https://github.com/ABDELAALI-ENNAMAT/Swiggy_Data_analysis.git

# 2. Navigate into the project directory
cd Swiggy_Data_analysis

# 3. Launch the Jupyter Notebook
jupyter notebook Swigy.ipynb
```

### View the Dashboard

Click the badge below to open the live Power BI report:

[![Power BI](https://img.shields.io/badge/View%20Dashboard-Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://app.powerbi.com/reportEmbed?reportId=3bc300f1-90fa-4f85-8ccc-c27ae4e3f865&autoAuth=true&ctid=2e589d81-ea7a-4dc7-8fb2-84ba95cc947f)

---

## 👤 Author

<div align="center">

### **Abdelaali Ennamat**
*Data Analyst · Business Intelligence · Python & Power BI*

[![GitHub](https://img.shields.io/badge/GitHub-ABDELAALI--ENNAMAT-181717?style=for-the-badge&logo=github)](https://github.com/ABDELAALI-ENNAMAT)

</div>

---

<div align="center">

⭐ **If this project helped you or inspired you, drop a star!** ⭐

*Built with 🧡 and a passion for data-driven storytelling*

</div>