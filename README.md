# 📊 Superstore Sales & Profitability Analysis

**Turning sales data into actionable business insights with Tableau**

## 👋 Project Overview

This project analyzes Superstore's sales, profitability, discounting, and customer return data from **2023 to 2026**. Using data analysis and interactive Tableau dashboards, the project explores business performance, identifies potential profitability issues, and highlights opportunities to improve sales performance and customer experience.

The goal is to translate transactional data into meaningful insights that can support better business decisions.

## 🎯 Business Problem

Superstore generates sales across multiple regions, product categories, and customer segments. However, differences in sales performance, profit margins, discount levels, shipping durations, and product returns can make it difficult to identify where the business is performing well and where improvements are needed.

A high sales figure does not necessarily indicate high profitability. Similarly, discounting may encourage sales but can also reduce profit margins. Understanding these patterns can help the business make more informed decisions.

## 🚀 Project Objectives

- Evaluate sales and profit performance across regions, categories, and customer segments.
- Identify products and sub-categories with low or negative profitability.
- Examine the relationship between discount levels and profitability.
- Explore return-rate patterns across regions and product categories.
- Investigate shipping duration and its potential relationship with product returns.
- Develop actionable recommendations to improve profitable sales and customer experience.

## 🔎 Business Questions

This project addresses six key questions:

1. Which regions, product categories, and customer segments generate the highest and lowest sales and profits?
2. Which products generate high sales but low or negative profit?
3. How do discount levels relate to sales and profitability?
4. Which products, categories, regions, and customer segments have the highest return rates?
5. How does shipping performance vary by shipping mode and region, and could longer shipping times be associated with higher returns?
6. What actions could Superstore take to increase profitable sales while addressing potential customer-experience issues?

## 🗂️ Dataset Overview

The project uses a Superstore transactional sales dataset covering **2023–2026**, together with return information and regional manager assignments.

The data includes:

- **Order information:** Order ID, Order Date, Ship Date, and Ship Mode
- **Customer information:** Customer ID, Customer Name, and Segment
- **Geographical information:** Country/Region, City, State/Province, Postal Code, and Region
- **Product information:** Product ID, Product Name, Category, and Sub-Category
- **Financial information:** Sales, Quantity, Discount, and Profit
- **Return information:** Order IDs associated with returned orders
- **Regional management information:** Manager assignments by region

**Dataset source:** https://public.tableau.com/app/learn/sample-data (Superstore Sales)

The dataset was used for educational and portfolio analysis purposes. Please refer to the original source for applicable usage and redistribution terms.

## 🧹 Data Preparation

Before analysis, the dataset was reviewed to assess data quality and consistency.

Key preparation activities included:

- Reviewing column names, data types, and the transaction-level structure.
- Checking missing values and duplicate records.
- Validating order and shipping dates.
- Checking category labels and text consistency.
- Reviewing numerical values, including zero sales, negative profits, and potential outliers.
- Checking relationships between orders, customers, products, returns, and regional managers.
- Matching return records to the sales dataset to identify returned and non-returned orders.

Negative profit values and potential outliers were not automatically removed, as they may represent meaningful business transactions.

For the detailed validation process and data-handling decisions, see [`docs/project_documentation.md`](docs/project_documentation.md).

## ⚙️ Data Transformation

Additional fields were created to support time-based, operational, and profitability analysis.

| Derived field | Purpose |
|---|---|
| Year, Quarter, Month, Month Number | Analyze trends over time |
| Weekday and Weekday Number | Compare performance by day of the week |
| Shipping Days | Measure the time between order and shipping dates |
| Discount Band | Group discount levels for comparison |
| Return Status | Identify returned and non-returned orders |
| Regional Manager | Connect regional performance with manager assignments |
| Profit Margin | Evaluate profit relative to sales |
| Sales per Unit | Examine sales relative to quantity |
| Profit per Unit | Examine profit relative to quantity |

Detailed calculation logic and implementation notes are documented separately.

## 🛠️ Tools Used

- **Microsoft Excel** — Dataset review, preparation, and supporting calculations, where applicable.
- **Tableau** — Data exploration, calculated fields, visualizations, and interactive dashboards.
- **GitHub** — Project versioning, documentation, and portfolio presentation.
- **Tableau Public** — Publishing and sharing interactive dashboards.

## 📈 Tableau Dashboards

The project is organized into four dashboards, each designed to answer a different set of business questions.

### 1. 📌 Executive Overview

Provides a high-level view of overall business performance.

Key components:
- Sales, profit, profitability, and other performance indicators
- Monthly sales and profit trends
- Regional performance comparisons
- Category performance
- State/province-level geographical map

The map provides a geographical perspective on the selected measure and complements the regional comparison charts.

🔗 **Dashboard:** https://public.tableau.com/views/Superstore_17918771767440/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

### 2. 🏆 Product Profitability

Examines which products and sub-categories contribute to profit and which may require further investigation.

Key components:
- Category and sub-category performance
- Sales versus profit analysis
- Top 10 products based on the selected metric
- Product profitability table
- Interactive metric selection

🔗 **Dashboard:** https://public.tableau.com/views/Superstore_17918771767440/ProductProfitability?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

### 3. 💸 Discount Analysis

Explores how discount levels relate to sales and profitability.

Key components:
- Discount levels and profit
- Profit margin by discount band
- Profit distribution across discount bands

The analysis helps identify discount levels associated with weaker profitability. The observed relationship should not be interpreted as proof that discounts alone caused lower profits.

🔗 **Dashboard:** https://public.tableau.com/views/Superstore_17918771767440/DiscountAnalysis?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

### 4. 📦 Customer Experience

Examines product returns and shipping duration to identify patterns that may warrant further investigation.

Key components:
- Return-rate comparisons across regions and categories
- Return-rate heatmap
- Shipping duration by return status

Return-rate results should be interpreted carefully because return records are associated with orders, while the sales dataset contains individual order lines.

🔗 **Dashboard:** https://public.tableau.com/views/Superstore_17918771767440/ReturnsCustomerExperience?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

## 💡 Key Findings

The following findings summarize selected results from the analysis. Monetary values are shown in the dataset's reporting currency.

### 📊 Overall Business Performance

- In 2026, sales were approximately **$745.57K** and profit was approximately **$95.93K**.
- Compared with 2025, sales increased by approximately **21.44%**, while profit increased by approximately **16.04%**.
- Profit margin decreased from approximately **13.5% to 12.9%**, a decline of about **0.6 percentage points**.
- The return rate increased from approximately **5.7% in 2025 to 6.1% in 2026** in the current analysis; this result should be validated against the distinct-order calculation.

### 🌍 Regional Performance

- The West region recorded approximately **$258.2K in sales** and **$45.4K in profit**, making it the strongest region by these measures.
- The Central region generated approximately **$147.9K in sales** but only **$7.6K in profit**, suggesting an opportunity to investigate its profitability.

### 🛍️ Product Profitability

- Technology generated approximately **$272.4K in sales** and **$50.8K in profit**.
- Furniture generated approximately **$219.3K in sales** but only **$3.3K in profit**.
- Several products recorded negative profit, including selected 3D printers, printers, and furniture products.
- Some sub-categories, such as Tables and Bookcases, recorded negative profit margins in the analysis.

### 💸 Discount Patterns

Profit margins varied substantially across discount bands:

| Discount band | Profit margin |
|---|---:|
| No Discount | 29.6% |
| Low | 11.9% |
| Medium | -15.3% |
| High | -77.4% |

Higher discount bands were associated with weaker profitability in this dataset. Further investigation is needed before drawing causal conclusions or changing pricing policies.

### 📦 Returns and Shipping

- Some region-category combinations showed relatively high return rates and may warrant further investigation.
- Shipping-duration distributions for returned and non-returned orders were broadly similar, with median shipping duration around four days.
- The current analysis did not show clear evidence that returned orders generally took longer to ship.

*These findings are descriptive and depend on the quality of the underlying data and calculations. Return-rate figures and product-level return patterns should be validated before operational decisions are made.*

## ✅ Business Recommendations

Based on the observed patterns, Superstore could consider the following actions:

1. **🔍 Investigate low-profit products.** Review product costs, selling prices, discount practices, and supplier arrangements before deciding whether to reprice, renegotiate, or discontinue individual products.

2. **💰 Review discount policies.** Assess whether medium and high discounts generate enough additional sales to justify their impact on profit. Consider product-specific discount limits rather than applying a single rule to all products.

3. **🌍 Examine regional profitability.** Investigate why the Central region generates comparatively low profit relative to sales. Compare its product mix, discount patterns, and operating costs with stronger-performing regions.

4. **📦 Investigate return patterns.** Validate high return rates and examine return reasons, product quality, customer feedback, and order details before introducing corrective actions.

5. **🚚 Continue monitoring shipping performance.** Track shipping duration by shipping mode and region, while investigating return reasons rather than assuming shipping delays are responsible for returns.

6. **📈 Monitor performance regularly.** Use the dashboards to track sales, profit, profit margin, returns, and discount performance over time.

## 🧭 Recommended Next Steps for the Business

To move from descriptive analysis to more targeted business action, Superstore should:

- Validate return-rate calculations using distinct orders and a clearly defined denominator.
- Investigate the costs and return reasons of low-profit and frequently returned products.
- Compare equivalent year-to-date periods when evaluating 2026 against 2025 if 2026 data is incomplete.
- Review discount effectiveness at product and sub-category levels.
- Establish regular KPI monitoring and investigate unusual changes in performance.

## ⚠️ Limitations

- **Incomplete reporting period:** 2026 may not represent a full year. Year-over-year comparisons should use equivalent periods where necessary.
- **Association versus causation:** The relationship between discounts and profitability does not prove that discounts alone caused lower profit.
- **Return-rate interpretation:** Returns are recorded at the order level, while sales data may contain multiple product lines per order. Incorrect joins or denominators can distort return-rate calculations.
- **Limited operational context:** The dataset may not include detailed product costs, reasons for returns, customer complaints, or product quality information needed to explain every pattern.
- **Geographical interpretation:** The map displays the selected measure at the state/province level but does not explain the underlying causes of performance differences.

## 📁 GitHub Project Structure

The repository is organized to separate the project overview, detailed documentation, dashboard screenshots, and any shareable data files.

```text
superstore-sales-analysis/
│
├── README.md
│
├── docs/
│   └── project_documentation.md
│
├── screenshots/
│   ├── executive_overview.png
│   ├── product_profitability.png
│   ├── discount_analysis.png
│   └── customer_experience.png
│
├── data/                     # Optional: shareable data only
│   └── README.md              # Dataset source and access notes
│
└── LICENSE                    # Optional
```

**Folder guide:**

- `README.md` — Introduces the project, key findings, recommendations, and dashboard links.
- `docs/project_documentation.md` — Contains the detailed data validation, cleaning, transformation, analysis methodology, and supporting explanations.
- `screenshots/` — Contains images of the four Tableau dashboards.
- `data/` — Optional folder for data that you have permission to redistribute. If the original dataset cannot be shared, document its source and access instructions instead.
- `LICENSE` — Optional file defining how others may use your original project materials. Check the dataset's terms separately; a repository license does not automatically grant rights to third-party data.

## 📚 Detailed Documentation

For the complete explanation of the data validation, preparation, transformations, analysis methodology, and technical decisions, see:

➡️ **[Read the full project documentation](docs/project_documentation.md)**

## 🙏 Acknowledgements

- Dataset provider: [Insert the original dataset creator or source]
- Tools: Microsoft Excel, Tableau, Tableau Public, and GitHub, as applicable to the completed workflow.

Please acknowledge the original dataset source and follow its usage and redistribution requirements.

## 👋 Conclusion

This project demonstrates how transactional sales data can be analyzed to evaluate business performance, investigate profitability challenges, explore discount patterns, and identify customer-experience issues.

By combining data preparation, calculated measures, visual analysis, and interactive Tableau dashboards, the project turns raw sales records into findings that can guide further business investigation and decision-making.

**The central takeaway:** Increasing sales is important, but sustainable business performance also requires attention to profitability, discount effectiveness, regional differences, and customer returns.

## 🎤 Project Presentation

Want a concise walkthrough of the analysis and business insights?

- 📄 **[View the PDF version](presentation/Superstore_Presentation.pdf)** 

The presentation highlights the main findings, business implications, and recommended next steps.
