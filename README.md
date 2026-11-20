# Project Background
Gamezone is a global e-commerce company founded in 2018 that sells new and refurbished gaming products worldwide through its website and mobile app.

The company collects substantial amounts of transactional and customer data, including purchase history, product information, marketing channels, purchasing platforms, geographic locations, and order fulfillment details. This data provides an opportunity to identify sales trends, understand product performance, and evaluate the factors contributing to changes in revenue.

This project analyzes Gamezone's e-commerce data from 2019 to 2021 to uncover business insights and support data-driven decision-making across sales, product, and marketing operations.


Insights and recommendations are provided on the following key areas:

- **Sales Performance:** Analyze overall revenue trends over time, identify significant changes in monthly sales, and investigate periods of unusually high or low performance. 
- **Product Performance:** Evaluate sales distribution across products, identify top-performing products, and investigate which products contributed most to changes in overall reveneue. 
- **Marketing & Regional Performance:** Examine sales distribution across marketing channels and geographic regions to understand their contributions to overall revenue and identify opportunities for futher investigation. 


The SQL queries used to inspect and clean the data for this analysis can be found here [link].

Targed SQL queries regarding various business questions can be found here [link].

An interactive Tableau dashboard used to report and explore sales trends can be found here [link].



# Data Structure & Initial Checks

The analysis uses Gamezone's e-commerce database, which includes transactional and regional information.

The available documentation identifies the following tables:

- **Orders:** Contains transaction-level information, including user IDs, order IDs, purchase and shipping timestamps, product details, prices, marketing channels, account creation methods, and geographic information.
  
- **Region:** Contains regional information used to validate and support geographic analysis.

The dashboard reports 21,864 total orders.

[Entity Relationship Diagram here]

### Data Quality Checks

Initial data exploration identified several data quality issues, including inconsistent date formats, missing values, inconsistent product names, and duplicate order IDs.

These issues were evaluated based on their magnitutde and whether they could be reliably resolved.

Key data cleaning actions included:
* Standardizing 10 purchases timestamps with inconsistent date formats
* Correcting 61 inconsistent product names.
* Recategorizing 83 missing marketing channels and 83 missing account creation methods as "Unknown."
* Correcting 9 missing, inconsistent, or invalid regional values using reference information.

Issues that could not be reliably resolved were retained rather than making unsupported assumptions. These are discussed further in the Assumptions and Caveats section.

# Executive Summary

### Overview of Findings

Gamezone generated approximately $6.15 million in sales across 21,864 orders, with an average order value (AOV) of $281. Sales more than doubled in early 2020, reaching significant peaks in September and December 2020, before declining in early 2021. Product-level analysis identified gaming monitors, PlayStation, and Nintendo Switch products as major contributors to sales performance, while direct marketing was the dominant sales channel.

The analysis suggests that the 2021 decline was not isolated to a single product or geographic region, indicating a broader business trend that warrants further investigation.

Explain the overarching findings, trends, and themes in 2-3 sentences here. This section should address the question: "If a stakeholder were to take away 3 main insights from your project, what are the most important things they should know?" You can put yourself in the shoes of a specific stakeholder - for example, a marketing manager or finance director - to think creatively about this section.

[Visualization, including a graph of overall trends or snapshot of a dashboard]



# Insights Deep Dive
### Overall Sales Performance

* **Sales increased significantly in early 2020.** Total sales more than doubled compared to the earlier period, reaching all-time highs in September and December 2020.
  
* **Sales declined significantly in early 2021.** Following the strong performance in 2020, revenue dropped considerably in the first months of 2021, indicating a change in the company's sales trajectory.
  
* **The December 2020 sales spike was observed across multiple products.** Almost all products experienced increased sales during this period, suggesting a potentially broader seasonal or company-wide impact rather than an isolated product trend.
  
* **Monthly sales varied considerably throughout the analysis period.** Initial exploratory analysis showed monthly sales ranging from approximately $80k to $500k across 2019-2021.

[Visualization specific to category 1]


### Product Performance

* **Gaming monitors were the top-performing product.** Gaming monitors generated nearly $2 million in total sales, making them the largest contributor to Gamezone's product revenue.
  
* **PlayStation, gaming monitors, and Nintendo Switch were major contributos to the 2021 sales decline.** All three products exhibited similar declining or plateauing sales patterns in early 2021.
  
* **The December 2020 sales spike was consistent across almost all products.** This suggests a potential seasonal effect, promotional campaign, or broader increase in customer demand.
  
* **Gaming headsets were identified as the weakest-performing product category in the initial analysis.** Further investigation is needed to determine whether this reflects lower customer demand, product availability, or potential data completeness issues.

[Visualization specific to category 2]


### Marketing & Regional Performance

* **Direct marketing was the dominant sales channel.** Sales attributed to direct traffic significantly exceeded those of other marketing channels.
  
* **Other marketing channels contributed comparatively smaller sales volumes.** Further investigation is needed to understand the effectiveness of social media, email, and other marketing strategies.
  
* **All geographic regions exhibited similar sales declines in early 2021.** The consistency across regions suggests that the decline was not isolated to a particular geographic market.
  
* **Regional sales followed the broader company-wide trend.** Sales increased throughout 2020 before declining in early 2021, reinforcing the need to investigate broader business or market conditions.

[Visualization specific to category 3]

# Recommendations:

Based on the insights and findings above, the following recommendations are intended for the Gamezone's finance, product, and marketing teams:

* Sales more than doubled in early 2020 before declining significantly in early 2021. **Investigate potential changes in market conditions, customer demand, pricing, and business operations to understand the drivers behind this shift.**
  
* Gaming monitors generated nearly $2 million in sales, while PlayStation, gaming monitors, and Nintendo Switch contributed significiantly to the 2021 decline. **Prioritize these products for further analysis, including pricing trends, inventory availability, and regional performance.**
  
* Direct marketing was the dominant contributor to sales. **Evaluate existing direct marketing strategies and investigate opportunities to improve the performance of other channels, particularly social media and email marketing.**
  
* Almost all products experienced a sales spike in December 2020. **Review historical promotional campaigns, seasonal demand, and marketing activities during this period to identify strategies that could be replicated.**
  
* All regions experienced similar declines in early 2021. **Investigate company-wide and external factors rather than focusing exclusively on individual geographic markets.**
  


# Assumptions and Caveats:

Throughout the analysis, several assumptions were made to manage challenges with the data. These assumptions and caveats are noted below:

* **Missing purchase timestamps:** One record contained a missing purchase date. Since the magnitude of this is low and there is no way to infer it, the missing data was left as is.

* **Missing or zero-dollar transactions:** 34 records contained missing or zero-dollar prices. These values were retained due to low in magnitude. However, in reality, we would need to check with stakeholders.

* **Missing marketing channels & account creation methods:** 83 records of marketing channel and 83 records of account creation method were recategorized as "Unknown".

* **Missing country codes:** 37 records contained missing country codes. They were retained due to low volume, but need to check with stakeholders.

* **Duplicate order IDs:** 145 records contained duplicate order IDs. They could be deleted because the magnitude is low. In this case, the records were left as is.

* **Shipping timestamps before purchase timestamps:** Approximately 2,000 records (9.15%) contained shipping timestamps earlier than their corresponding purchase timestamps. These values were retained but should be flagged for further investigation before conducting detailed shipping and fulfillment analysis.

* **Missing and inconsistent regional values:** 9 regional records were corrected using reference information.
