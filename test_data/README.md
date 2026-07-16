# Test Data — Automotive Companies Dataset

This folder contains sample automotive industry company datasets for testing the **Data Import & Company Analysis** module of the Automotive Inventory Visibility and Tracking System (AIVTS).

## Files

| File | Format | Description |
|---|---|---|
| `automotive_companies.csv` | CSV | Comma-separated values file with all 20 company records |
| `automotive_companies.xlsx` | Excel | Multi-sheet Excel workbook — main data + industry summary |
| `automotive_companies.json` | JSON | Structured JSON with metadata envelope and company array |

## Dataset Overview

The dataset contains **20 anonymized-but-realistic** automotive industry companies representing the Indian automotive supply chain ecosystem, including OEMs (Original Equipment Manufacturers), two-wheeler makers, commercial vehicle manufacturers, and auto component suppliers.

### Record Count
- **20 company records** across all three files

---

## Column / Field Reference

| Column Name | Type | Required | Description | Example |
|---|---|---|---|---|
| `company_name` | String | ✅ Yes | Full legal name of the company | `Tata Motors Ltd` |
| `industry` | String | ✅ Yes | Industry or sector classification | `Automobile Manufacturing` |
| `revenue` | Number | ✅ Yes | Annual revenue in USD | `3440000000` |
| `employee_count` | Number | ✅ Yes | Total number of full-time employees | `82000` |
| `founding_year` | Number | ✅ Yes | Year the company was founded | `1945` |
| `location` | String | ✅ Yes | City and country of primary operations | `Mumbai, India` |
| `headquarters` | String | Optional | Specific headquarters city | `Mumbai` |
| `website` | String | Optional | Company website URL | `www.tatamotors.com` |
| `ceo` | String | Optional | Name of current CEO/MD | `Shailesh Chandra` |
| `stock_symbol` | String | Optional | Stock exchange ticker symbol | `TATAMOTORS` |
| `market_cap` | Number | Optional | Market capitalisation in USD | `25000000000` |
| `description` | String | Optional | Brief company description | `One of India's largest...` |

---

## Industries Represented

| Industry | Companies |
|---|---|
| Automobile Manufacturing | 6 |
| Two-Wheeler Manufacturing | 3 |
| Auto Components | 5 |
| Commercial Vehicles | 2 |
| Tyre Manufacturing | 2 |
| Battery Manufacturing | 1 |
| Forging & Engineering | 1 |

---

## File-Specific Details

### `automotive_companies.csv`

- **Encoding:** UTF-8
- **Delimiter:** Comma (`,`)
- **Header row:** Row 1
- **Date format:** N/A (founding_year is a plain integer)
- **Numeric values:** Stored as plain numbers (no currency symbols or commas)

**Loading in AIVTS:** Select CSV format, upload the file. All 12 columns will be detected. The 6 required columns (`company_name`, `industry`, `revenue`, `employee_count`, `founding_year`, `location`) will pass validation automatically.

---

### `automotive_companies.xlsx`

- **Sheets:**
  - Sheet 1 — `Automotive Companies`: Full dataset with all 20 rows and 12 columns. Header row is row 1 (styled in blue).
  - Sheet 2 — `Industry Summary`: Aggregated view with industry-level totals (for reference; AIVTS reads Sheet 1).
- **Column widths:** Pre-formatted for readability.

**Loading in AIVTS:** Select Excel format, upload the file. AIVTS reads the **first sheet** automatically.

---

### `automotive_companies.json`

Structure:
```json
{
  "metadata": {
    "source": "Sample Dataset",
    "version": "1.0",
    "record_count": 20,
    "description": "..."
  },
  "companies": [
    {
      "company_name": "Tata Motors Ltd",
      "industry": "Automobile Manufacturing",
      "revenue": 3440000000,
      ...
    },
    ...
  ]
}
```

AIVTS automatically detects the nested `companies` array. Flat JSON arrays (without a metadata wrapper) are also supported.

---

## Column Naming Conventions

The AIVTS Data Import module accepts **flexible column name variations**. The following aliases are recognised for each required column:

| Required Field | Accepted Column Names |
|---|---|
| `company_name` | company_name, company name, name, company, organization, org_name |
| `industry` | industry, sector, category, business_type, business type |
| `revenue` | revenue, annual_revenue, annual revenue, sales, turnover, income |
| `employee_count` | employee_count, employees, headcount, staff, workforce, num_employees |
| `founding_year` | founding_year, founded, year_founded, established, year established |
| `location` | location, city, headquarters, hq, region, country, place |

---

## Usage Notes

1. **Numbers:** Revenue and market_cap are stored in **USD** (full integers, not millions/billions).
2. **No null values:** All required fields are populated in the sample data. When building your own dataset, ensure required fields are not blank.
3. **Parquet:** A Parquet version is not included because Parquet requires a binary encoding tool. You can convert `automotive_companies.csv` to Parquet using Python: `pd.read_csv('automotive_companies.csv').to_parquet('automotive_companies.parquet')`.

---

## Quick Start

```bash
# Using the test data
1. Open AutoInventoryTracker.html in your browser
2. Log in with any account (password: password)
3. Click "Data Import & Analysis" in the sidebar
4. Drag and drop any file from this folder onto the upload zone
5. Review the validation summary and data preview
6. Click "Import & Analyse" to load the data
```
