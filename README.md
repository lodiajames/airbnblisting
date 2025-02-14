### TITLE 
Analysing New York City Airbnb Listings Trends and Insights using sql and tableau.

### Table of Content
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Findings](#findings)
- [Recommendation](#recommendation)
- [Limitations](#limitations)
- [References](#references)

### Project Overview
This project explores the new York City Airbnb open Data dataset to uncover trends in short-term rentals. Using SQL and Tableau, i analysed room type distribution, geographic density, pricing and review trends to provide actionable insights for hosts and travelers.

### Data Sources
Type Here
[Download here](https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data)

### Tools
- SQL  (Data Exploration)
- Tableau (Visualization)


### Data Cleaning
Data Loading and Inspection
   - The data has some null value that does not affect the analysis. I prefer to remove in tableau the null values in order to give a precise or accurate insights.


### Exploratory Data Analysis

EDA Involving Exploring the sales data to answer key questions

### Data Analysis

1. Getting the whole information of the data

``` SQL
SELECT * FROM AIRBNB 
```
2. Checking the total number of listings:
   
``` SQL 
SELECT count(*) as total_listings from airbnb;

``` 
3. What are the distribution of room types
   
``` SQL 
SELECT room_type, COUNT(*) AS COUNT 
FROM airbnb
GROUP BY room_type
ORDER BY COUNT DESC

```
4. Average price by neighborhood group by (borough)

``` SQL  
SELECT neighbourhood_group, ROUND(AVG(price)) AS AVG_PRICE
FROM airbnb
GROUP BY neighbourhood_group
ORDER BY AVG_PRICE DESC

```
5. Most expensive listings
   
``` SQL 
SELECT name, neighboorhood, price
FROM airbnb
ORDER BY price DESC
LIMIT 10

```

6. Average time availability by neighboorhood group

``` SQL 
SELECT neightboorhood_group , ROUND(AVG(availablity_365)) as AVG_AVAILABILITY
FROM airbnb
GROUP BY neightbourhood_group
ORDER BY AVG_AVAILABILITY DESC

```
7. Listings with the lowest availability

```  SQL
SELECT name, neighbourhood_group, availablity_365
FROM airbnb
WHERE availability_365 < 30
ORDER BY availability_365 ASC

```
8. Top hosts with the most listings
   
``` SQL
SELECT host_id, COUNT(*) as NUM_LISTING
FROM airbnb
GROUP BY  host_id
ORDER BY num_Listing DESC
LIMIT 10

``` 
9. Average price by host
    
``` SQL 
SELECT host_id, ROUND(AVG(price)) AS Avg_Host_Price
from airbnb
GROUP BY host_id
ORDER BY Avg_Host_Price
LIMIT 10

```

10. Listings with the most reviews

``` SQL
SELECT name, neighboorhood, number_of_reviews
FROM airbnb
ORDER BY number_of_reviews DESC
LIMIT 10

```

11. Average reviews per month by neighborhood group

``` SQL 
SELECT neighbourhood_group, ROUND(AVG(reviews_per_month)) as Avg_Review_By_Month
FROM airbnb
GROUP BY neighbourhood_group
ORDER BY Avg_Review_By_Month DESC

```


### Findings

 1. **Room Type Distributions**
  -Analysed the distributions of room types (Entire Home/Apartment, Private Room, Shared Room) across NYC neighborhoods.
  - Found that **Entire Home/Apartement** listings dominate the market
- **Private Rooms** are more common in residential neighborhoods, offering budget-friendly options for travelers.
  
2. **Geographic Density**
   - Visualized the geographic distribution of Airbnb listings using Tableau.
   - Identified hotspots in Manhattan, Brooklyn, and Queens, with **Manhattan** having the highest concentration of listings.
     
3. **Pricing Trends**
   - Investigated pricing trends across neighborhoods and room types.
   - Discovered that **Manhattan** has the highest average nightly rates, while **Bronx** offers more affordable options.

### Tableau Dashboard
[Link to Tableau Dashboard](https://public.tableau.com/views/AIRBNB_17395535036030/AIRBNBDASHBOARD?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link) 

### Github Link
[Link to GitHub Repository](https://github.com/lodiajames/airbnblisting.git) 



 ### Limitations
 
The present data give is not the most recent upated version of AIRBNB Listing in New York and it might have some differences in term of data precision. But Overall it can gives us a well around analysis and discoveries.

 ### References

 [kaggle](https://www.kaggle.com/)


 #####
 This project not only enhanced my data analysis and visualization skills but also provided valuable insights into the short-term rental market in NYC. It demonstrates my ability to transform raw data into actionable business intelligence.
