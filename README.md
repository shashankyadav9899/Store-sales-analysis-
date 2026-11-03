# Ghaziabad Grocery Sales Dashboard

A Power BI dashboard and supporting datasets analysing **5,000 grocery and household orders** across eight Ghaziabad localities, from **1 Jan 2024 to 31 Dec 2025**.

## Project structure

```
ghaziabad-grocery-sales-dashboard/
├── dashboard/
│   └── dashboards.pbix        # Power BI report (open in Power BI Desktop)
├── data/
│   ├── sales.csv              # Raw order-level data (5,000 rows)
│   ├── sales_analysis.csv     # Sales & profit aggregated by customer segment
│   └── top_products.csv       # Currently identical to sales_analysis.csv (see note)
├── .gitignore
└── README.md
```

## File details

| File | Description | Size |
|------|-------------|------|
| `dashboard/dashboards.pbix` | Power BI report with one page (1920x1080) and 8 visuals, built on the `sales` table | ~231 KB |
| `data/sales.csv` | Order-level dataset, 5,000 rows, no missing values | ~538 KB |
| `data/sales_analysis.csv` | Summary by customer segment (5 rows) | 246 B |
| `data/top_products.csv` | Same content as `sales_analysis.csv` (segment summary, not products) | 246 B |

> **Note:** `top_products.csv` contains customer-segment data rather than a product ranking. It is likely a duplicate export. Replace it with a real top-products export, or delete it.

## Dataset: `sales.csv`

| Column | Type | Description |
|--------|------|-------------|
| `Order ID` | text | Unique ID, format `GZB-YYYYMMDD-NNNN` (GZB = Ghaziabad) |
| `Order Date` | date | 2024-01-01 to 2025-12-31 |
| `Region` | text | Locality (8 values) |
| `Category` | text | Product category (8 values) |
| `Product` | text | Product name (41 unique products) |
| `Customer Segment` | text | Buyer type (5 values) |
| `Sales` | number | Order sales value (INR) |
| `Profit` | number | Order profit (INR) |

**Regions:** Indirapuram, Raj Nagar Extension, Vasundhara, Vaishali, Sahibabad, Kaushambi, Crossings Republik, Loni

**Categories:** Grocery & Staples, Packaged Foods, Fruits & Vegetables, Household & Cleaning, Personal Care, Dairy & Frozen, Beverages, Home & Kitchen

**Customer segments:** Regular Household, Small Business / Kirana, Bulk Buyer / Society, Young Professional, Senior Citizen

## Dashboard visuals

1. Column chart: Sales by Region
2. Map: Sales by Region
3. Donut chart: Sales by Customer Segment
4. Line chart: Sales by month
5. Clustered bar chart: Sales by Product
6. Card: Sum of Profit
7. Slicer: Year
8. Slicer: Region

## Key figures

- **Total sales:** ₹26,29,558
- **Total profit:** ₹2,66,113 (about 10.1% margin)
- **2024:** sales ₹13,68,640, profit ₹1,40,205
- **2025:** sales ₹12,60,918, profit ₹1,25,908
- **Top region:** Indirapuram (₹5,45,819)
- **Top product:** India Gate Basmati Rice 5kg (₹2,81,712)
- **Top segment:** Regular Household (₹10,75,788)
- **Highest-profit category:** Home & Kitchen (₹82,042); Fruits & Vegetables has the thinnest margin

### Sales by customer segment (`sales_analysis.csv`)

| Segment | Total sales | Total profit |
|---------|------------:|-------------:|
| Regular Household | 1,075,788.30 | 109,153.48 |
| Bulk Buyer / Society | 586,977.87 | 55,315.23 |
| Small Business / Kirana | 582,163.87 | 63,256.39 |
| Young Professional | 212,693.97 | 21,881.28 |
| Senior Citizen | 171,934.25 | 16,506.50 |

## How to use

1. Clone the repo: `https://github.com/shashankyadav9899/Store-sales-analysis`
2. Open `dashboard/dashboards.pbix` in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (Windows).
3. If visuals show no data, go to **Transform data > Data source settings** and point the `sales` table at `data/sales.csv`.

## Tools

 Excel Power BI Desktop, CSV data.

## Author

shashank yadav
