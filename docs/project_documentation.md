# 📊 Superstore Sales Analysis
### Project Documentation

**Project type:** Data Analytics Portfolio Project  
**Analysis period:** 2023–2026  
**Tools:** Microsoft Excel, Tableau Public  
**Author:** Marceline Setiawan   
**Date completed:** October 2026

---

## 📌 1. Project Overview

This project analyzes Superstore sales transactions from 2023 to 2026 to evaluate business performance, understand factors affecting profitability, and identify opportunities to improve the customer experience.

The analysis covers sales and profit trends, regional performance, product profitability, discount effectiveness, product and category performance, return rates, and shipping duration. Microsoft Excel was used to inspect, clean, validate, and prepare the dataset, while Tableau was used to develop interactive dashboards for exploring business performance.

The project translates transaction-level data into actionable business insights to help management make more informed decisions about pricing, discount strategies, product performance, regional opportunities, and customer experience.

The project is guided by the following business question:

**How can Superstore improve customer experience and identify opportunities to increase profitable sales?**

## 🎯 2. Business Problem

Sales growth does not necessarily mean that a business is becoming more profitable. Products with high sales may generate low or negative profit, while excessive discounting may reduce profit margins. Return patterns and shipping performance may also reveal areas that require further investigation.

Superstore therefore needs to understand not only how much it sells, but also where its profit comes from, which products contribute to losses, how discounts relate to profitability, and where customer-experience issues may occur.

This analysis examines these areas to identify business strengths, potential risks, and opportunities for improvement.

## 🎯 3. Project Objectives

The objectives of this project were to:

- 📈 Evaluate sales, profit, profit margin, and order trends over time.
- 🌍 Compare business performance across regions, states, and provinces.
- 🛍️ Identify the categories, sub-categories, and products contributing to sales and profit.
- 💰 Investigate products with high sales but low or negative profit.
- 🏷️ Examine the relationship between discount levels and profitability.
- 🔄 Compare return rates across relevant business dimensions.
- 🚚 Analyze shipping duration and compare shipping patterns for returned and non-returned orders.
- 💡 Develop practical recommendations to support profitable growth and better customer experience.

## ❓ 4. Business Questions

The analysis was organized around six main questions.

1. **Regional and category performance:** Which regions, product categories, and customer segments generate the highest and lowest sales and profit?
2. **Product profitability:** Which products generate high sales but low or negative profit?
3. **Discount effectiveness:** How do discount levels relate to sales and profitability?
4. **Returns and customer experience:** How do return rates vary across regions, product categories, and other available business dimensions?
5. **Shipping performance:** How does shipping duration vary, and do returned orders show different shipping-duration patterns from non-returned orders?
6. **Business recommendations:** What actions could help Superstore increase profitable sales while addressing potential customer-experience issues?

## 🗂️ 5. Dataset Overview

The project uses Superstore transaction data covering **2023–2026**.

The dataset contains order-level identifiers and individual transaction-line records. A single order may contain multiple products, meaning that one Order ID can appear across multiple rows. This distinction is important when calculating order counts, average order value, and return rates.

### 5.1 Main Data Fields

| Field | Description |
|---|---|
| Order ID | Identifier for an order |
| Order Date | Date the order was placed |
| Ship Date | Date the order was shipped |
| Ship Mode | Shipping service or method |
| Customer ID / Customer Name | Customer identifiers and names |
| Segment | Customer segment |
| Country/Region | Country or broader geographic designation |
| City | City associated with the transaction |
| State/Province | State or province associated with the transaction |
| Postal Code | Geographic postal identifier |
| Region | Business region |
| Product ID / Product Name | Product identifiers and descriptions |
| Category / Sub-category | Product classification |
| Sales | Sales amount |
| Quantity | Units purchased |
| Discount | Discount applied |
| Profit | Profit recorded for the transaction |

The workbook also contains a Returns sheet listing orders identified as returned and a regional-manager mapping sheet linking managers to regions.

### 5.2 Data Scope

- **Analysis period:** 2023–2026.
- **Data granularity:** Individual transaction lines.
- **Geographic analysis:** Region and state/province.
- **Product analysis:** Category, sub-category, and product.
- **Customer analysis:** Customer segment and available customer-related fields.
- **Return analysis:** Return records matched to sales transactions using Order ID.
- **Shipping analysis:** Shipping duration derived from Order Date and Ship Date.

**Dataset source:** [[Superstore Sales](https://public.tableau.com/app/learn/sample-data)]

## 🧹 6. Data Cleaning and Validation

Before conducting the analysis, the dataset was reviewed and prepared to improve consistency and reliability.

### 6.1 Data Structure and Data Types

The structure of the workbook and the roles of the available fields were examined. Identifiers, dates, categorical fields, and numerical measures were distinguished so that each could be used appropriately in the analysis.

Date fields were reviewed as dates, while Sales, Profit, Quantity, and Discount were treated as numerical measures. Identifier fields such as Order ID and Product ID were retained as identifiers rather than treated as additive numerical values.

### 6.2 Missing Values and Duplicate Records

Missing values were reviewed to identify potential issues affecting the analysis. Duplicate records were also examined to distinguish possible duplicate transactions from repeated identifiers that occur naturally in transaction-level data.

Repeated Order IDs were not automatically treated as duplicates because a single order can contain multiple product lines.

### 6.3 Date Validation

Order Date and Ship Date were examined for date consistency. Records with impossible or inconsistent date sequences were reviewed, including cases where the Ship Date preceded the Order Date.

The analysis period was also checked against the intended reporting period of 2023–2026.

### 6.4 Text and Category Consistency

Categorical fields, including Region, Category, Sub-category, Segment, and Ship Mode, were reviewed for inconsistent labels and formatting that could affect grouping and comparison.

Geographic fields were also considered when preparing the state/province-level map, particularly because postal codes and geographic naming conventions can differ between locations.

### 6.5 Numerical Data Review

Sales, Profit, Quantity, and Discount were reviewed for unusual values, zeros, negative values, and potential outliers.

Negative profit was retained as a meaningful business result rather than automatically removed. Loss-making transactions are important to identifying products and discount patterns that may reduce overall profitability.

### 6.6 Relationship and Lookup Checks

Related fields and supporting sheets were examined to support consistent analysis.

- Product IDs were considered alongside product names and product classifications.
- Order IDs were used to connect sales records with return information.
- Regions were used to associate transactions with the regional-manager mapping.
- Date fields were used to derive reporting periods and shipping duration.

These checks supported the preparation of the dataset for analysis and visualization.

## ⚙️ 7. Data Transformation and Calculated Fields

Several additional fields and measures were prepared to support more detailed analysis.

### 7.1 Date-Based Fields

Date fields were used to derive:

- **Year:** Groups transactions by year.
- **Quarter:** Groups transactions into quarterly reporting periods.
- **Month:** Supports monthly sales and profit trends.
- **Month Number:** Supports chronological month sorting.
- **Weekday:** Identifies the day of the week on which an order was placed.
- **Weekday Number:** Supports chronological weekday sorting.

These fields enable the comparison of performance over time and help reveal seasonal or recurring patterns.

### 7.2 Shipping Days

Shipping duration was calculated as:

**Shipping Days = Ship Date − Order Date**

The resulting value represents the elapsed number of calendar days between the order date and shipping date.

This measure was used to compare shipping-duration distributions, including differences between returned and non-returned orders.

### 7.3 Discount Band

Discount values were grouped into discount bands to simplify comparison of profitability at different discount levels.

The bands were organized in the following order:

1. No Discount
2. Low
3. Medium
4. High

The custom sorting order keeps the categories in a logical sequence rather than relying on alphabetical sorting.

### Discount-Band Thresholds

| Discount Band | Discount Percentage |
|---|---|
| No Discount | 0% |
| Low | Greater than 0% and up to 20% |
| Medium | Greater than 20% and up to 40% |
| High | Greater than 40% |

These discount bands were created in Excel to categorize discount levels for profitability analysis. The thresholds follow the classification logic defined in the Excel formula.

### 7.4 Return Status

The Returns sheet was matched with the sales data using Order ID to classify orders as:

- **Returned**
- **Not Returned**

This classification supports comparisons between returned and non-returned orders and the calculation of return-related measures.

### 7.5 Profit Margin

Profit margin measures the proportion of sales retained as profit.

**Profit Margin = Total Profit ÷ Total Sales**

For aggregated reporting, total profit is divided by total sales for the relevant group or reporting period. This provides an overall margin measure rather than simply averaging individual transaction margins.

### 7.6 Sales per Unit

**Sales per Unit = Sales ÷ Quantity**

This measure helps examine the sales amount relative to the number of units sold.

### 7.7 Profit per Unit

**Profit per Unit = Profit ÷ Quantity**

This measure helps compare the profit contribution associated with each unit sold.

### 7.8 Order-Based Measures

Order-level analysis used distinct Order IDs where appropriate, because the dataset contains multiple transaction lines for some orders.

Key measures included:

- **Total Sales:** Sum of Sales.
- **Total Profit:** Sum of Profit.
- **Profit Margin:** Total Profit divided by Total Sales.
- **Total Orders:** Count of distinct Order IDs.
- **Average Order Value (AOV):** Total Sales divided by distinct orders.
- **Returned Orders:** Distinct orders classified as returned.
- **Return Rate:** Returned orders divided by total distinct orders.

These measures support comparisons across years, regions, categories, products, and other available dimensions.

## 🔍 8. Analysis Methodology

The analysis used descriptive and comparative methods to summarize business performance and investigate patterns in the dataset.

### 8.1 Trend Analysis

Sales, profit, profit margin, and order volume were compared across years and months. Year-over-year comparisons were used to examine changes in business performance.

### 8.2 Regional Analysis

Sales and profit were compared across business regions. A state/province-level map was added to provide a more detailed geographic view of the selected measure.

The map complements the regional comparison charts. It helps viewers examine the geographic distribution of performance but does not, by itself, explain why particular locations perform differently.

### 8.3 Product Profitability Analysis

Product and sub-category results were compared using sales, profit, and profitability measures. Products with substantial sales but negative profit were examined to identify possible areas for pricing, discount, cost, or product-strategy review.

### 8.4 Discount Analysis

Profitability was compared across discount bands. The analysis examined whether higher discount levels were associated with lower profit margins and whether some discount bands showed negative profitability.

These comparisons identify patterns in the observed data; they do not independently establish that discounts caused a particular profit outcome.

### 8.5 Return Analysis

Return rates were compared across available dimensions, including region and product category. A heatmap was used to make relatively high and low return-rate combinations easier to identify.

The analysis uses the return classification derived from the Returns sheet and the existing validated return-rate calculations.

### 8.6 Shipping Analysis

Shipping duration was compared by return status to examine whether returned orders had a noticeably different shipping-duration distribution from non-returned orders.

This analysis focuses on the observed relationship between shipping duration and return status rather than assuming that shipping duration causes returns.

## 📊 9. Tableau Dashboard Development

Four Tableau dashboards were developed to present the analysis in a clear and interactive format.

### 9.1 Dashboard 1 — Executive Overview 📈

**Purpose:** Provide a high-level summary of Superstore's business performance.

The dashboard brings together key performance indicators and visualizations that allow viewers to assess overall results and identify areas that may require further investigation.

**Main components:**
- KPI cards summarizing business performance.
- Monthly sales and profit trends.
- Regional performance comparisons.
- Category performance comparisons.
- State/province-level map showing the geographic distribution of the selected measure.

**Business value:**

The Executive Overview helps management quickly assess overall performance, compare reporting periods, identify stronger and weaker regions, and explore how results are distributed geographically.

The map provides a state/province-level perspective that complements the regional charts rather than replacing them.

**Dashboard link:** [Executive Overview](https://public.tableau.com/views/Superstore_17918771767440/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

### 9.2 Dashboard 2 — Product Profitability 🛍️

**Purpose:** Identify the products and product groups that contribute to or reduce profitability.

**Main components:**
- Category and sub-category performance.
- Sales versus profit scatter plot.
- Top 10 products ranked by the selected metric.
- Product profitability table.
- Interactive metric selection for comparing different performance measures.

**Business value:**

The dashboard helps users distinguish high-sales products from genuinely profitable products. It also supports the investigation of loss-making products and product groups whose sales contribution may not translate into satisfactory profit.

**Dashboard link:** [Product Profitability](https://public.tableau.com/views/Superstore_17918771767440/ProductProfitability?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

### 9.3 Dashboard 3 — Discount Analysis 🏷️

**Purpose:** Examine how discount levels relate to profitability.

**Main components:**
- Discount and profit analysis.
- Profit margin by discount band.
- Profit distribution across discount bands.

**Business value:**

The dashboard makes it easier to identify discount levels associated with weaker profitability and to investigate whether discount practices may need further review.

The findings can support more selective discount strategies that balance sales volume with profit contribution.

**Dashboard link:** [Discount Analysis](https://public.tableau.com/views/Superstore_17918771767440/DiscountAnalysis?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

### 9.4 Dashboard 4 — Customer Experience 🔄

**Purpose:** Explore return patterns and shipping-duration differences.

**Main components:**
- Return-rate comparisons.
- Return-rate heatmap by region and product category.
- Shipping-duration comparison for returned and non-returned orders.

**Business value:**

The dashboard helps identify region-category combinations with relatively high return rates and investigate whether shipping duration differs between returned and non-returned orders.

These patterns can guide further investigation into potential customer-experience issues. Return rates alone do not establish the reasons behind returns.

**Dashboard link:** [Customer Experience](https://public.tableau.com/views/Superstore_17918771767440/ReturnsCustomerExperience?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## 📈 10. Key Findings

The following findings summarize the results obtained from the analysis.

### 10.1 Overall Business Performance

| Year | Sales | Profit | Profit Margin | Distinct Orders | Average Order Value |
|---|---:|---:|---:|---:|---:|
| 2023 | $493,659.72 | $51,660.94 | 10% | 995 | $496.14 |
| 2024 | $472,993.03 | $62,020.97 | 13% | 1,053 | $449.19 |
| 2025 | $613,933.58 | $82,665.20 | 13% | 1,340 | $458.16 |
| 2026 | $745,567.53 | $95,926.35 | 13% | 1,723 | $432.71 |
| **Total** | **$2,326,153.86** | **$292,273.46** | **13%** | **5,111** | **Approx. $455.17** |

*Note: Profit margins are rounded. Total average order value is calculated from total sales divided by total distinct orders.*

Overall, the business generated approximately **$2.33 million in sales and $292,273 in profit** during the analysis period.

Sales increased from approximately $613,934 in 2025 to $745,568 in 2026, representing growth of approximately **21.44%**. Profit also increased, from approximately $82,665 to $95,926, representing growth of approximately **16.04%**.

However, profit grew more slowly than sales. The profit margin declined from approximately 13.5% in 2025 to 12.9% in 2026, a decrease of about **0.6 percentage points**.

Distinct orders increased from 1,340 in 2025 to 1,723 in 2026. Meanwhile, average order value declined from $458.16 to $432.71.

**Interpretation:** The business experienced sales growth and higher overall profit in 2026. However, the lower average order value and declining profit margin indicate that increased sales volume did not translate into proportional improvements in profitability.

### 10.2 Regional Performance 🌍

The West region recorded approximately **$258,200 in sales and $45,400 in profit**, making it the strongest region by these measures in the analyzed results.

The Central region generated approximately **$147,900 in sales and $7,600 in profit**. Its profit contribution was relatively low compared with its sales.

**Interpretation:** The West region provides a useful reference for understanding stronger regional performance. The Central region deserves closer investigation to identify whether particular products, discount practices, or other factors contribute to its relatively weak profit performance.

The state/province-level map complements this analysis by showing the geographic distribution of the selected business measure.

### 10.3 Category and Sub-Category Performance 🛒

Technology generated approximately **$272,400 in sales and $50,800 in profit**. Office Supplies generated approximately **$253,800 in sales and $41,700 in profit**.

Furniture generated approximately **$219,300 in sales but only $3,300 in profit**.

At the sub-category level, Paper, Envelopes, and Labels recorded relatively strong profit margins:

| Sub-Category | Profit Margin |
|---|---:|
| Labels | 43.9% |
| Paper | 43.4% |
| Envelopes | 42.3% |
| Tables | -8.5% |
| Bookcases | -3.1% |
| Supplies | -2.5% |

**Interpretation:** Technology and Office Supplies were important contributors to sales and profit. Furniture generated meaningful sales but relatively little profit, indicating a need to investigate the factors affecting its profitability.

The negative margins for Tables, Bookcases, and Supplies highlight sub-categories that may require closer review.

### 10.4 Loss-Making Products ⚠️

Several products recorded substantial sales but negative profit.

| Product | Sales | Profit | Profit Margin | Average Discount |
|---|---:|---:|---:|---:|
| Cubify Cube 3D Printer | $11,100.00 | -$8,880.00 | -80.0% | 53.33% |
| Lexmark MX611dhe Mono… | $16,829.90 | -$4,590.00 | -27.3% | 40.00% |
| Cubify Cube 3D Printer… | $8,000.00 | -$3,840.00 | -48.0% | 50.00% |
| Chromcraft Bull-Nose… | $9,917.60 | -$2,876.10 | -29.0% | 28.00% |

**Interpretation:** These products demonstrate that high sales do not necessarily result in positive profit. The high average discounts observed for several loss-making products suggest that discounting may be one factor worth investigating.

Other possible explanations include product costs, pricing decisions, or the composition of the transactions. These factors should be examined before deciding on specific corrective actions.

### 10.5 Discount and Profitability Analysis 🏷️

The analysis identified substantial differences in profit margin across discount bands.

| Discount Band | Profit Margin |
|---|---:|
| No Discount | 29.6% |
| Low | 11.9% |
| Medium | -15.3% |
| High | -77.4% |

**Interpretation:** The results show a strong negative relationship between the observed discount bands and profitability in this dataset. The No Discount band recorded the highest profit margin, while the Medium and High bands recorded negative margins.

This suggests that discount practices deserve careful review. However, the results should not be interpreted as proof that discounts alone caused the losses, because product mix, costs, pricing, and other transaction characteristics may also affect profitability.

### 10.6 Return Rate and Customer Experience 🔄

The validated return analysis showed the following year-over-year results:

| Measure | 2025 | 2026 |
|---|---:|---:|
| Returned Orders | 77 | 105 |
| Return Rate | 5.7% | 6.1% |

Returned orders increased from 77 to 105, representing an increase of approximately **36.36%**. The return rate increased from 5.7% to 6.1%, a rise of **0.4 percentage points**.

The return-rate heatmap also highlighted several region-category combinations with relatively high return rates in the analyzed results:

| Region | Category | Return Rate |
|---|---|---:|
| West | Fasteners | 20.27% |
| West | Machines | 19.51% |
| West | Appliances | 19.12% |
| West | Chairs | 16.58% |
| West | Paper | 16.58% |

**Interpretation:** The increase in both returned-order count and return rate suggests that return performance deserves attention as sales volume grows. The heatmap helps narrow the investigation to specific region-category combinations.

These findings identify where further investigation may be useful; they do not, by themselves, explain why customers returned their orders.

### 10.7 Shipping Duration 🚚

The comparison of shipping duration for returned and non-returned orders showed broadly similar distributions, with median shipping duration of approximately four days for both groups.

The analysis did not reveal a clear difference indicating that returned orders consistently took longer to ship.

**Interpretation:** Based on the observed shipping-duration patterns, there is no clear evidence that longer shipping duration is associated with returns in this dataset. Other possible explanations for returns would require additional information, such as return reasons, product condition, delivery complaints, or customer feedback.

## 💡 11. Business Recommendations

Based on the findings, the following actions are recommended.

### 11.1 Review Discount Strategies

**Finding:** Profit margins declined substantially across higher discount bands, with negative margins in the Medium and High bands.

**Recommendation:**
- Review discount policies for products with weak or negative profitability.
- Establish minimum acceptable profit-margin thresholds before applying large discounts.
- Evaluate discount effectiveness using both sales and profit, rather than sales volume alone.
- Review whether targeted promotions can achieve sales objectives without excessively reducing margins.

**Expected benefit:** Better control over discount-related profitability risks.

### 11.2 Investigate Loss-Making Products

**Finding:** Several products generated considerable sales but recorded negative profit.

**Recommendation:**
- Review pricing, product costs, and discount levels for identified loss-making products.
- Investigate whether the losses are consistent across transactions or concentrated in particular orders.
- Consider repricing, reducing discounts, renegotiating costs, or changing promotional priorities where supported by further analysis.
- Avoid discontinuing products based only on a single aggregate result without considering their wider business role.

**Expected benefit:** Better product-level decisions and reduced avoidable losses.

### 11.3 Improve Furniture Profitability

**Finding:** Furniture generated meaningful sales but comparatively little profit, while Tables and Bookcases recorded negative profit margins.

**Recommendation:**
- Review profitability by Furniture sub-category and product.
- Examine whether discounts, product costs, or the mix of products sold explain the weak results.
- Prioritize corrective action for products with repeated negative profit.

**Expected benefit:** Improved profit contribution from an important sales category.

### 11.4 Investigate Regional Profit Differences

**Finding:** The West region generated strong sales and profit, while Central generated relatively low profit compared with sales.

**Recommendation:**
- Examine the Central region's product mix, discount patterns, and sub-category profitability.
- Compare the results with stronger regions to identify practices or product combinations worth investigating.
- Use the state/province map alongside regional charts to identify geographic areas for more detailed analysis.

**Expected benefit:** More targeted regional decisions based on profitability rather than sales alone.

### 11.5 Monitor Return Performance

**Finding:** The return rate increased from 5.7% in 2025 to 6.1% in 2026, while returned orders increased from 77 to 105.

**Recommendation:**
- Monitor return rate and returned-order count over time.
- Investigate the region-category combinations highlighted by the heatmap.
- Where possible, collect and analyze return reasons to distinguish product-related issues from delivery, fulfillment, or customer-expectation issues.
- Evaluate corrective actions using subsequent return-rate trends.

**Expected benefit:** Better identification of potential return-related issues and more targeted customer-experience improvements.

### 11.6 Avoid Assuming Shipping Duration Causes Returns

**Finding:** Returned and non-returned orders showed broadly similar shipping-duration distributions.

**Recommendation:**
- Continue monitoring shipping performance, but do not assume that reducing shipping duration alone will reduce returns.
- Investigate additional variables, particularly return reasons, product quality, fulfillment accuracy, and customer feedback, if these become available.

**Expected benefit:** Customer-experience improvements based on evidence rather than unsupported assumptions.

### 11.7 Balance Sales Growth with Profitability

**Finding:** Sales and profit increased in 2026, but profit grew more slowly than sales and profit margin declined.

**Recommendation:**
- Track sales growth alongside profit margin and profit contribution.
- Evaluate promotions and sales initiatives using profitability measures.
- Monitor average order value and product mix to understand the composition of sales growth.

**Expected benefit:** A more balanced approach to growth that considers both revenue and profitability.

## 🧭 12. Project Limitations

The following limitations should be considered when interpreting the results.

### 12.1 Historical Data

The findings describe the observed period from 2023 to 2026. Historical patterns do not guarantee future performance.

### 12.2 Descriptive Analysis

The project primarily uses descriptive and comparative analysis. Relationships observed between discount levels, profitability, shipping duration, and return status do not independently establish causation.

### 12.3 Limited Return-Reason Information

The available Returns sheet identifies returned orders but does not, in the data used for this analysis, provide sufficient information to establish the reasons for each return. As a result, the analysis identifies patterns but cannot definitively explain the underlying causes.

### 12.4 Return Data Granularity

Return information is linked using Order ID. Where an order contains multiple products, order-level return information may not identify which individual product was returned. Product-level return conclusions should therefore be limited to what the available data can directly support.

### 12.5 Shipping Analysis

Shipping duration was calculated using the difference between Order Date and Ship Date. This measures the elapsed time between ordering and shipping, not the complete delivery time to the customer. The analysis also does not establish whether shipping duration caused a return.

### 12.6 External Business Factors

The dataset does not fully capture all factors that may influence profitability, such as changes in supplier costs, competitor pricing, operational decisions, product quality, or broader market conditions.

### 12.7 Geographic Interpretation

The state/province map displays the geographic distribution of the selected measure. Geographic patterns alone do not explain the causes of performance differences between locations.

## 🛠️ 13. Tools and Skills Applied

### Tools

- **Microsoft Excel:** Data inspection, cleaning, validation, calculations, and preparation.
- **Tableau Public:** Data visualization, calculated measures, interactive worksheets, and dashboard development.

[Add other tools here only if you actually used them in this project.]

### Skills Demonstrated

- Data cleaning and preparation.
- Data validation and quality checks.
- Data transformation and calculated fields.
- KPI definition and performance measurement.
- Exploratory and descriptive data analysis.
- Sales and profitability analysis.
- Return-rate and shipping-duration analysis.
- Data visualization and dashboard design.
- Business interpretation and evidence-based recommendations.
- Communicating findings to a business audience.

## 📚 14. Conclusion

This project demonstrates how transaction-level data can be transformed into business insights through data preparation, descriptive analysis, and interactive visualization.

The analysis found that Superstore generated approximately $2.33 million in sales and $292,273 in profit across 2023–2026. Sales and profit increased in 2026, but the decline in profit margin suggests that sales growth did not translate into proportional profitability improvement.

The analysis also identified loss-making products, substantial profitability differences across discount bands, weak profitability in selected Furniture sub-categories, and an increase in the return rate from 2025 to 2026. Meanwhile, returned and non-returned orders showed broadly similar shipping-duration distributions.

The four Tableau dashboards present these findings from complementary perspectives: overall business performance, product profitability, discount effectiveness, and customer experience.

The main business takeaway is that **sustainable growth requires more than increasing sales**. Superstore should also monitor profitability, investigate loss-making products, review discount strategies, and use return-rate patterns to guide further investigation into customer-experience issues.

Through this project, I applied data analytics techniques to a business problem and practiced communicating findings through interactive dashboards and practical recommendations.

## 🔗 15. Project Resources

- **Tableau Public — [Executive Overview](https://public.tableau.com/shared/76K5BX2J4?:display_count=n&:origin=viz_share_link)**
- **Tableau Public — [Product Profitability](https://public.tableau.com/views/Superstore_17918771767440/ProductProfitability?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**
- **Tableau Public — [Discount Analysis](https://public.tableau.com/views/Superstore_17918771767440/DiscountAnalysis?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**
- **Tableau Public — [Customer Experience](https://public.tableau.com/views/Superstore_17918771767440/ReturnsCustomerExperience?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**
- **PowerPoint Presentation: [View the PDF version](presentation/Superstore_Presentation.pdf)**
- **Project Repository: [Repository](https://github.com/setiawanmarceline/superstore-sales-analysis)**
- **Dataset Source: [Superstore Sales](https://public.tableau.com/app/learn/sample-data)**

## 🙏 16. Acknowledgements

This project was completed as part of my data analytics learning and portfolio development. It provided an opportunity to apply data preparation, analysis, visualization, and business communication skills to a practical sales-analysis scenario.

**Data source acknowledgement:** [Superstore Sales](https://public.tableau.com/app/learn/sample-data)


