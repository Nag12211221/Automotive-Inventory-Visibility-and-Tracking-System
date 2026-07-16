# Automotive Inventory Visibility and Tracking System

A fully standalone, zero-dependency web application for real-time automotive inventory management.

## 🚀 How to Use

1. Download **`AutoInventoryTracker.html`**
2. Open it in any modern web browser (Chrome, Firefox, Edge, Safari)
3. No installation, no internet connection, no server required
4. Log in with any demo account (password: `password`)

## 👤 Demo User Accounts

| Account | Role | Access Level |
|---|---|---|
| Administrator | Full access to all modules | View, Edit, Delete, Admin |
| Operations Manager | Operations management | View, Edit |
| Warehouse Executive | Stock and parts management | View, Edit |
| Data Analyst | Read-only dashboards and reports | View only |

## 📦 Modules Included

| Module | Description |
|---|---|
| **Inventory Dashboard** | Real-time stock visibility across all locations |
| **Vehicle Tracking** | VIN-level vehicle movement and lifecycle tracking |
| **Spare Parts Inventory** | SKU-level parts tracking and stock management |
| **Transit Tracking** | Track shipments and get delay alerts |
| **Stock Audit** | Physical vs system stock verification |
| **Reorder Management** | Low stock alerts and purchase order tracking |
| **Aging Inventory** | Identify slow-moving and dead stock |
| **Damage Management** | Track damaged vehicles/parts with insurance workflows |
| **Supplier Management** | PO tracking and vendor performance analytics |
| **Allocation Management** | Assign vehicles to dealer bookings/customers |
| **Alerts & Escalations** | Automated notifications and escalation management |
| **Reports & Analytics** | BI dashboards with CSV export |
| **Data Import & Analysis** | Import company data (CSV/Excel/JSON/Parquet) for analysis |
| **User Roles & Audit Logs** | Access control and complete system audit trail |

## 📥 Data Import & Company Analysis

The **Data Import & Analysis** module (new in v2.0) allows you to load external company datasets for analysis and insights.

### Supported File Formats

| Format | Extensions | Offline? |
|---|---|---|
| CSV | `.csv` | ✅ Yes |
| Excel | `.xlsx`, `.xls` | CDN on first use |
| JSON | `.json` | ✅ Yes |
| Parquet | `.parquet` | CDN on first use |

### Required Columns

Your data file must include these six columns (flexible naming supported):

| Field | Accepted Names |
|---|---|
| `company_name` | company_name, name, company, organization |
| `industry` | industry, sector, category, vertical |
| `revenue` | revenue, annual_revenue, sales, turnover |
| `employee_count` | employee_count, employees, headcount, staff |
| `founding_year` | founding_year, founded, year_founded |
| `location` | location, city, headquarters, hq, region |

### Analysis Features

- **KPI Summary** — Total companies, industries, average revenue, average employee count
- **Industry Distribution** — Bar chart ranked by company count
- **Geographic Distribution** — Top 8 headquarters locations
- **Revenue Distribution** — Bucketed into 4 ranges (< $100M to > $5B)
- **Employee Scale** — Bucketed into 4 size tiers
- **Top 5 by Revenue** — Ranked table with industry, employees, and founding year
- **Key Insights** — Automated text summary (totals, dominant industry, oldest/newest company)
- **CSV Export** — Download the full imported dataset at any time

### Test Data

Sample datasets are available in [`/test_data`](./test_data/) — see the [Test Data README](./test_data/README.md) for details.

## 📄 Documentation

A comprehensive PDF user guide is available in [`/docs/AIVTS_User_Guide.pdf`](./docs/AIVTS_User_Guide.pdf), covering:

- Overview and module reference
- Installation and setup
- Data Import: supported formats, column conventions, and troubleshooting
- Analysis walkthrough with test data
- Export options
- FAQ (14 questions)
- Appendix: file structure, audit log reference, keyboard tips

## 💾 Data Storage

All inventory data is stored in your browser's **localStorage** — no data leaves your device.
Use the **"Clear All Data"** button in the sidebar to permanently delete all stored data and start fresh.

> **Note:** Imported company data (via the Data Import module) is held in-memory only and will need to be re-imported after a page refresh.

## 🖥️ System Requirements

- Any modern web browser (Chrome 90+, Firefox 88+, Edge 90+, Safari 14+)
- No internet connection required for core features (CSV/JSON import and all inventory modules)
- Excel and Parquet parsing load a library from CDN on first use
- No installation required
