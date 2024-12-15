# Task Details 
[1] Get lowest local price
1. Get name, address, open times, menu items, & prices for Village from Yelp API
2. Get top-rated 5 restaurants in 2 km with similar menu items
3. DISPLAY menu items & prices for Village + each restaurant

[2] Get busy times & bad weather
4. Get Village busy times from GMaps API
5. Get temperature & rain near Village
6. DISPLAY both

[3] DISPLAY Village menu with predicted prices using ANY ML algo:
IF
7.1 Temp is < 45 deg. Fahrenheit (note API returns Kelvin, convert to F)
7.2 It will snow or get moderate or heavy rain
7.3 Village is busier than usual
THEN
Price should be more than lowest local price
ELSE
Price should be lowest local price

SUBMISSION
1. Github code link
2. How to run
3. Display outputs for each step on a webpage or console

# Analysis Workflow for Village the Soul of India
1. Restaurant Details Retrieval:
We began by extracting the name, address, and open status of the restaurant Village the Soul of India from Yelp.

2. Menu Information Extraction:
Navigating to the restaurant's menu page on the Yelp website, we scraped the menu details, including item names and prices.

3. Competitor Identification:
Using the Yelp API, we retrieved a list of competitors within a 2 km radius offering similar cuisine categories. Each competitor’s name and Yelp rating were collected. The list was then sorted by ratings in descending order to identify the top five competitors.

4. Competitor Menu Analysis:
For each of the top five competitors, we accessed their respective menu pages and scraped detailed menu information.

5. Menu Comparison:
Leveraging the RapidFuzz library, we compared the menu items of Village the Soul of India with those of its competitors. This allowed us to identify similar dishes and analyze the pricing differences for each competitor.

6. Data Merging:
All gathered data, including competitor details, menu comparisons, and pricing information, were merged into a single dataset. Despite encountering numerous null values during this process, we proceeded to the next stage while planning for null value reduction in subsequent steps.

7. Null Value Reduction*:
Efforts were made to minimize the null values and get a more comprehensive dataset.

8. Popular Times Data:
By utilizing the pytz and datetime libraries, we identified the current day of the week and hour. To enhance our analysis, we incorporated data on the restaurant’s popular times (rush hours) by referencing a GitHub repository and integrating details obtained via the Google Maps API.

9. Weather Information:
Using the OpenWeather API, we fetched the current temperature and weather description to analyze how external factors might influence pricing and demand.

10. Dynamic Pricing Determination:
With the collected data, we implemented conditional logic to determine whether menu prices should align with the lowest local prices or exceed them based on the context.

11. Final Data Frame:
A comprehensive dataframe was created, showcasing:
i) Menu items of Village the Soul of India
ii) Suggested real-time pricing (considering competitor pricing, weather, and rush hours)
iii) Original prices from the Yelp menu
This structured approach ensured a detailed competitive analysis and data-driven insights for dynamic pricing strategies.

