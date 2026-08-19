# 📊 Sales Performance Dashboard

Interactive **Business Intelligence dashboard developed in Power BI** to analyse sales performance, monitor key business indicators and identify trends across products, countries and time periods.

## 🎯 Project Objective

The objective of this project is to transform sales data into clear and actionable business insights through an interactive Power BI report.

The dashboard allows users to:

- Monitor overall sales performance and units sold.
- Analyse monthly sales trends.
- Compare product performance.
- Evaluate sales performance across countries.
- Identify the highest-performing country dynamically.
- Explore detailed sales information using interactive filters and report navigation.

## 🛠️ Tools & Technologies

- **Power BI**
- **Power Query**
- **DAX**
- **Microsoft Excel**
- Data Cleaning
- Data Visualization
- KPI Analysis
- Business Intelligence

## 📈 Dashboard Overview

The main dashboard provides an executive overview of sales performance through KPIs, interactive filters and visual analysis.

![Sales Performance Dashboard](Imágenes/dashboard-overview.png)

### Main KPIs

- **Total Sales:** 118.73M
- **Units Sold:** 1.13M
- **Top Country:** dynamically calculated according to the current filter context.

## 🧮 DAX Implementation

A custom DAX measure was created to dynamically identify the country with the highest sales:

```DAX
Top Country =
VAR CountryTable =
    TOPN(
        1,
        SUMMARIZE(
            'financials',
            'financials'[Pais],
            "TotalSales", SUM('financials'[Ventas])
        ),
        [TotalSales], DESC
    )
RETURN
    MAXX(CountryTable, 'financials'[Pais])
```

The measure responds dynamically to the filter context of the report, allowing the top-performing country to update according to user selections.

## 🔎 Detailed Sales Analysis

A second report page provides a more detailed view of sales performance.

![Detailed Sales Analysis](Imágenes/detailed-sales-analysis.png)

This view enables analysis of:

- Sales by country and product.
- Units sold by product and country.
- Sales distribution across business segments.
- Country sales performance.
- Detailed sales records.
- Interactive filtering and report navigation.

## 💡 Key Insights

The analysis highlights:

- Differences in sales performance across countries.
- Monthly variations in product demand.
- Products and markets with stronger sales performance.
- Changes in sales behaviour throughout the analysed period.
- The value of interactive filtering for deeper business analysis.

## ⚙️ Dashboard Features

- Multi-page Power BI report
- Interactive filters
- Report navigation
- Dynamic KPI calculations
- Custom DAX measure
- Product and country analysis
- Monthly sales trend analysis
- Business-oriented data visualization

## 📂 Repository Structure

```text
power-bi-sales-dashboard/
│
├── Imágenes/
│   ├── dashboard-overview.png
│   └── detailed-sales-analysis.png
│
├── sales-performance-dashboard.pbix
│
└── README.md
```

The complete Power BI report is available in:

**`sales-performance-dashboard.pbix`**

## 👩‍💻 Author

**Luisa Fernanda Salazar García**

Computer Engineer  
Master's Degree in Big Data & Visual Analytics — Expected September 2026

**Data & BI:** Power BI · Tableau · SQL · Excel · Data Visualization · Business Intelligence
