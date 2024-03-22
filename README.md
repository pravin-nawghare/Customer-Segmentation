
# Project Title

Customer Insights Analyzer: Cohort and RFM Analysis

## Index
- [Overview](#Overview)
- [Dependencies](#Dependencies)
- [Usage](#Usage)
- [Data](#Data)
- [Cohort Analysis](#Cohort_Analysis)
- [RFM Analysis](#RFM_Analysis)
- [Results](#Results)

## Overview
This project is a comprehensive toolkit designed to _explore and understand_ __customer behavior patterns__. Leveraging __Cohort and RFM (Recency, Frequency, Monetary)__ analysis techniques, the project offers businesses invaluable insights into _customer segmentation and purchasing trends_. Through meticulous data analysis and visualization, the businesses can now make _informed decisions, optimize their marketing strategies and enhance customer retention efforts_. This project serves as a _toolkit_ for businesses aiming to gain a competitive edge in today's dynamic market landscape by analysing customer behaviour.
## Dependencies

* numpy==1.25.2
* matplotlib==3.7.1
* seaborn==0.13.1
* pandas==1.5.3
* dataprep==0.4.5
* math module
* datetime
    
## Usage
This project combines Cohort analysis and RFM analysis. As both of them are very powerful tool for understanding customer behavior and developing targeted strategies to improve customer lifetime value. 
* Targeted Retention Strategies: By combining insights from cohort analysis and RFM analysis, _targeted retention strategies_ can be developed.
* Personalized Marketing: RFM analysis helps identify high-value customer segments which can be useful for _personalize marketing campaigns and promotions_ for these valuable customers.
* Product Development: Analyze RFM segments alongside product usage data, it can help to identify features or functionalities that resonate best with high-value customers, informing product development efforts.
* _Deeper Customer Understanding_: Combining cohort analysis and RFM analysis provides a comprehensive view of customer behavior, acquisition patterns, and value over time.
* Data-Driven Decision Making: This analysis provide data-driven insights to support marketing, product development, and customer success initiatives.
* Improved Customer Retention: By identifying at-risk segments and high-value segments, companies can develop __targeted strategies__ to _reduce churn and increase customer lifetime value._
By using Cohort analysis and RFM analysis together, you can gain valuable customer insights and develop more effective strategies to acquire, retain, and grow your customer base.



## Data
Dataset shape: (235574,5)

Dataset Metadata
Column  | Dtype  |  Description
------------- | -------------  |-----------
country  | object  |  Country code where the order has been delivered
id  | int64  |  Customer id
week.year  |  object  |  Date of purchase in week and year format (week are week of the year)
revenue  |  float64  |  Total price paid by the customer for the delivered product
units  |  int64  |  Number of units delivered

### Data cleaning, Pre-processing and Observations

* The dataset contains _week.year_ column which was spilt into two seperate columns __week and year__ column. By using the two new column a __date__ column was also introduced.
* It has been observed that the data dosen't contain any null values, which may have been affected our further calculations, but there were some duplicates which we got rid of.
* The _country_ column contains country code of 18 countries, by using __dataprep library__ the full name from the country code was derived.
(add piechart here)
* By observing the purchasing patterns of customers from different countries it is evident that __Indonesia(21.3%), Vitenam(12.2%), India(11.6%), China(8.8%) and Philippines(8.6%)__ these countries bagged top 5 positions for most orders delivered., whereas __Malayasia and Uzbekistan__ were in bottom two.
(add revenue chart here)
* It is quite evident that __Indonesia(21.86%), China(17.16%) and India(10.84%)__ contribute for most part of the revenue generation. Unlikely _Vitenam_ has most number of orders after Indonesia but it dosen't got it's place in top 5 countries contributing for most revenue generation. 

(add monthly revenue graph)

* At January, 2019 the revenue was 25M USD which was _linearly increasing_ upto April, 19 but saw sharp decline after that.
* This pattern continued till November,19 but _December,19_ was a month which generated the most revenue more than __45M USD__.
* Again shrap decline was seen, and the same trend of decline and rise continued till October,2020.
* However November, 2020 again got the peak with bagging more than __40M USD__ as revenue, _highest overall in the year 2020_.   




				




## Cohort Analysis
__Cohort Analysis__ is a powerful technique used to track and analyze the behavior of specific groups of customers over time. In this project, cohort analysis plays a crucial role in understanding _customer retention, engagement, and purchasing patterns_. By organizing customers into cohorts based on shared characteristics or experiences, such as sign-up date or first purchase date, we can uncover trends and identify areas for improvement in customer lifecycle management. The cohort analysis process implemented in this project involves _segmentation, retention rate calculation, and visualization of cohort trends_.

* For doing cohort analysis from date column _Cohort_Month_ was found which gives the date of first occurence of the customer.
* _Cohort Index_ gives us for how many months or cohorts the customer was active. There were in total 23 cohort index.
* Grouping the data on _Cohort_Month and Cohort Index_ total number of customers fall into each category was calculated.

There are three main ways to read the cohort chart:
* __Horizontally(row)__ _(upto the lifetime of customer)_: analyze a single cohort’s retention rates over time _e.g.,_ the decreasing retention rates for cohort_month 1 across 23 months.
* __Vertically(column)__ _(upto the lifetime of product)_: analyze month-wise retention rates among cohorts. _E.g.,_ compare October 2019 metrics with any cohort_month.
* __Diagonally__: find retention rates for a specific month over all cohorts _e.g.,_ compare August 2019 retention rates across all cohorts diagonally.





## RFM (Recency, Frequency, Monetary) Analysis
__RFM Analysis__ is a method used to __segment and analyze customers__ based on their _recent purchase behavior, frequency of purchases, and total monetary value spent_. In this project, RFM analysis serves as a key component for _identifying_ and understanding customer segments with _high potential value_. By assigning RFM scores to each customer, we can categorize them into different groups, such as high-value, loyal customers or at-risk customers. 
* __Recency__: How recently has the customer made a transaction.
* __Frequency__: How frequent is the customer in ordering/buying some product.
* __Monetary__: How much does the customer spend on purchasing products.
The RFM analysis process involves calculating RFM scores for each customer, _segmenting customers based on these scores_, and visualizing the findings to derive actionable insights for marketing and sales strategies.

* The values of recency, frequency and monetary was calculated and the whole dataset is ranked based on these values.
* The _more_ the frequency and monetary values, higher ranks was awarded but on the contrary _lower recency value_ is considered a good thing. 
* From the rank, scores were calculated and using the __Percentrank.inc__ formula for customer segmentation.
**Segment Description**
* **Champions**: Bought recently, buy often, and spend the most.
* **Frequent Shoppers**: Buy on a regular basis and are responsive to promotions.
* **Recent Engagers**: Recent customers with average frequency.
* **Occasional Buyers**: Bought most recently, but not often.
* **Exploratory Visitors**: Recent shoppers who haven’t spent much.
* **High-Value Prospects**: Above-average recency, frequency, and monetary values. May not have bought very recently though.
* **At-Risk Customers**: Below-average recency and frequency. We need to reactivate them.
*  **Lapsed Loyalists**: Purchased often but a long time ago. We need to bring them back!
* **Dormant Clients**: Used to purchase frequently but haven’t returned for a long time.
*  **Ghost Clients**: Purchased a long time ago and never came back.




## Results
#### Cohort Analysis
(add graph here)
Customer Retention
* __Strong initial retention__ across all cohorts, but there is a _significant drop_ in customers between the _first month and the second month_. Then the retention rate stabilizes around __30-40%__ for most cohorts. _This suggests that companies are successful at retaining a core group of customers after an initial drop-off_.
* _Early adopters_ show the __best retention__. The January 2019 cohort shows the _highest retention_ rate throughout the measured period. This could indicate that the product offering was a __good fit__ for the needs of this initial group of customers.
Customer Churn
* __High churn in the first month__. There is a __significant drop__ in customer retention between the _first month and the second month_ across all cohorts. This suggests that companies need to focus on efforts to improve customer onboarding and engagement during this critical period.
* Churn is __consistent__ over time. After the initial drop-off, the churn rate remains fairly consistent for most cohorts. This suggests that companies may be able to focus their churn reduction efforts on specific customer segments or product features.
__Future Scope:__ _The chart does not show the reason for customer churn. It would be beneficial to understand why customers are churning in order to develop targeted strategies to reduce churn._

(add retention rate here)
The most concerning aspect of this graph is the generally __downward trend__ in customer retention across cohorts. This indicates that, on average, customers are churning at a higher rate as time progresses.  Here are some possible reasons for this trend:
* __Lackluster onboarding experience__: New customers might not be getting the value for money or support they need early on, leading them to churn quickly.
* __Decreasing product satisfaction__: Over time, customers may become less satisfied with the product's features or functionality.
* __Heightened competition__: Increased competition in the market might be offering customers better alternatives.
__Specific Cohort Performance__
While there's a general downward trend, we can also see some variations in retention rates between cohorts. For instance:
* The cohort around _index 12_ appears to have a __steeper decline__ in retention compared to others. Investigate what marketing campaigns or product changes happened around that time to understand if they might have negatively impacted retention.
* The cohorts around index 18-20 seem to have a slightly _higher retention_ rate throughout the measured period. Analyze these cohorts to see if they share any characteristics related to acquisition channel, or demographics that could inform strategies to improve overall retention.
__Developing Targeted Strategies__

Given the downward trend, here are some initial strategies you can consider to improve customer retention:

* __Improve onboarding process__: Focus on creating a clear, informative, and engaging onboarding experience that effectively highlights the product's value proposition.
* __Gather customer feedback__: Proactively solicit feedback through surveys or user interviews to understand customer pain points and areas for improvement in the product or service.
* __Prioritize customer success__: Invest in resources and strategies to ensure customer success, such as providing excellent customer support, and creating a strong community around the product.
* __Personalize the user journey__: Segment your user base and tailor communication, promotions to their specific needs and interests. This can increase user engagement and satisfaction.
* __A/B test improvements__: Experiment with different onboarding flows, product features, and marketing campaigns to see what resonates best with your customer base and improves retention.






#### RFM Analysis
(add segment graph here)

Observations from segments formed.
* _Ghost Clients_ were the most populated segment with nearly 3500 customers followed by _High Value Prospects_ 3200 customers and _Recent Engagers_ 2800 customers.
* __Frequent Shoppers__ were the least populated segment with _Exploratory Visitors_ and _Occasional Buyers_ standing above them.
* Our most loyal customers __Champions__ with 2100 customers shared the place with __Dormant Clients__, having their position in the top 5 most populated customer segment.  
* All other segments were having number of customers less than 2000 in them.
Strategy for every customer segment
Customer Segment  |  Strategy
-------------  |  ------------
Champions  |  Provide exclusive rewards or VIP perks for continued loyalty.
Frequent Shoppers  |  Offer personalized promotions based on past purchase history to encourage repeat purchases.
Recent Engagers  |  Send targeted follow-up emails or offers to encourage their next purchase.
Occasional Buyers  |  Create incentives for repeat purchases, such as limited-time discounts or bundled deals.
Exploratory Visitors  |  Implement retargeting campaigns to remind them of their previous visit and encourage conversion.
High-Value Prospects  |  Provide personalized recommendations or special discounts to entice them to make a purchase.
At-Risk Customers  |  Offer incentives or special deals to win them back, such as reactivation discounts or loyalty rewards.
Lapsed Loyalists  |  Re-engage them with nostalgic marketing campaigns highlighting past positive experiences with the brand.
Dormant Clients  |  Reach out with targeted emails or offers to rekindle their interest and encourage them to return.
Ghost Clients  |  Send a personalized reactivation campaign with a compelling offer to encourage them to revisit the company.




