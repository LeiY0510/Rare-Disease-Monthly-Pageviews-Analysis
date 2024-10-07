# Rare-Disease-Monthly-Pageviews-Analysis
Analyze the monthly pageviews of rare disease articles on Wikipedia, accessed through both desktop and mobile devices, and to generate visualizations
README
*****************************************************************************************************************************************************************************************************************************************************************************
Project Title: 
Rare Disease Monthly Pageviews Analysis
Project Goal:
The goal of this project is to analyze the monthly pageviews of rare disease articles on Wikipedia, accessed through both desktop and mobile devices, and to generate three visualizations:
1. Maximum Average and Minimum Average page views for mobile and desktop.
2. Top 10 Peak Page Views for both mobile and desktop access.
3. Articles with the Fewest Months of Data for mobile and desktop access.
The data is retrieved from Wikimedia Foundation’s Pageviews API, processed into structured formats, and visualized using Python.
*****************************************************************************************************************************************************************************************************************************************************************************
Data License and Wikimedia Foundation Terms of Use:
The source data for this project is obtained via the Wikimedia Foundation's Pageviews API. According to the Wikimedia Foundation's Terms of Use (found here), the data is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License (CC BY-SA 3.0).
*****************************************************************************************************************************************************************************************************************************************************************************
Summary of ToU Application:
The dataset created through this project uses public pageview data from Wikimedia Foundation's API. This dataset adheres to the terms, allowing reuse and distribution, provided appropriate credit is given and any derivative works are shared under similar terms.
*****************************************************************************************************************************************************************************************************************************************************************************
Relevant API Documentation:
Wikimedia Foundation Pageviews API Documentation: https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews
	The Pageviews API provides access to Wikipedia page view statistics. This project specifically uses the per-article API to request monthly pageview data for rare disease articles.
*****************************************************************************************************************************************************************************************************************************************************************************
Intermediary and Output Files:

Intermediary Data Files:
1. rare-disease_monthly_mobile_201501-202304.json:
Contains the aggregated monthly pageviews data for mobile access (including mobile-app and mobile-web).
Format: JSON
2. rare-disease_monthly_desktop_201501-202304.json:
Contains the monthly pageviews data for desktop access.
Format: JSON

Final Output Files:
1. max_min_average_page_requests.png:
Visualization of articles with the maximum and minimum average page requests for both mobile and desktop access over the entire time period.
Format: PNG image file.
2. top_10_peak_page_views.png:
Visualization of the top 10 articles by peak page views for both mobile and desktop access.
Format: PNG image file.
3. fewest_months_of_data.png:
Visualization of the articles with the fewest months of available pageview data for both mobile and desktop access.
Format: PNG image file.
*****************************************************************************************************************************************************************************************************************************************************************************
Data Schema:
For each .json file:

1. Article Title: The title of the Wikipedia article.
2. Timestamp: The year and month of the pageview data in YYYYMM format.
3. Views: The number of pageviews recorded for that specific article in the given month.

*****************************************************************************************************************************************************************************************************************************************************************************
Example JSON Structure:

{
  "Article_Title_1": {
    "201501": 1200,
    "201502": 1400,
    ...
  },
  "Article_Title_2": {
    "201501": 900,
    "201502": 1100,
    ...
  }
}
*****************************************************************************************************************************************************************************************************************************************************************************
Known Issues or Special Considerations:
1. Some articles have very sparse data or even just a single month of page views. This may skew average calculations or result in incomplete trends.
2. Mobile access is split into two types by the Wikimedia API: mobile-app and mobile-web. The script aggregates both types under “mobile” for the purposes of this project.
3. Data may have gaps, which could be due to article creation dates (some articles may not have existed at the start of the time range) or incomplete collection from the API.
4. Wikimedia's Pageviews API enforces rate limiting (max 100 requests per second). The script includes a small throttle delay to avoid violating this limit.
5. Article titles retrieved from Wikipedia must be URL-encoded (spaces are replaced by underscores, special characters are encoded) before making API requests.
6. Data timestamps are provided in YYYYMM format and should be interpreted as UTC for monthly granularity.
