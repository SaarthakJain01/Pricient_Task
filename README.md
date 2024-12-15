# Village the Soul of India: Pricing Analysis

## Task Details

### [1] Get Lowest Local Price
1. Retrieve the name, address, open times, menu items, and prices for Village the Soul of India using the Yelp API.
2. Identify the top 5 restaurants within a 2 km radius offering similar menu items and having the highest ratings.
3. **Display** the menu items and prices for Village and each competitor restaurant.

### [2] Get Busy Times & Bad Weather
4. Retrieve Village's busy times from the Google Maps API.
5. Fetch the current temperature and rain information near Village using a weather API.
6. **Display** the busy times and weather data.

### [3] Display Village Menu with Predicted Prices Using Any ML Algorithm
#### Pricing Conditions:
- **If:**
  - Temperature is below 45°F (convert temperature from Kelvin to Fahrenheit).
  - It will snow or experience moderate to heavy rain.
  - Village is busier than usual.
- **Then:**
  - Prices should be higher than the lowest local price.
- **Else:**
  - Prices should match the lowest local price.

### Submission Requirements
1. Provide a GitHub link to the code.
2. Include instructions on how to run the solution.
3. Display outputs for each step on a webpage or console.

---

## Analysis Workflow for Village the Soul of India

### 1. Restaurant Details Retrieval
We began by extracting the name, address, and open status of the restaurant **Village the Soul of India** from Yelp.

### 2. Menu Information Extraction
Using the Yelp API, we navigated to the restaurant's menu page and scraped details such as menu item names and prices.

### 3. Competitor Identification
Using the Yelp API, we retrieved a list of competitors within a 2 km radius offering similar cuisine categories. Each competitor’s name and Yelp rating were collected. The list was then sorted by ratings in descending order to identify the top five competitors.

### 4. Competitor Menu Analysis
For each of the top five competitors, we accessed their respective menu pages and scraped detailed menu information.

### 5. Menu Comparison
We leveraged the **RapidFuzz** library to compare the menu items of Village the Soul of India with those of its competitors. This allowed us to identify similar dishes and analyze pricing differences for each competitor.

### 6. Data Merging
All gathered data, including competitor details, menu comparisons, and pricing information, were merged into a single dataset. Despite encountering numerous null values during this process, we proceeded to the next stage while planning for null value reduction in subsequent steps.

### 7. Null Value Reduction
Efforts were made to minimize the null values and obtain a more comprehensive dataset.

### 8. Popular Times Data
By utilizing the **pytz** and **datetime** libraries, we identified the current day of the week and hour. To enhance our analysis, we incorporated data on the restaurant’s popular times (rush hours) by referencing a GitHub repository and integrating details obtained via the Google Maps API.

### 9. Weather Information
Using the **OpenWeather API**, we fetched the current temperature and weather description to analyze how external factors might influence pricing and demand.

### 10. Dynamic Pricing Determination
With the collected data, we implemented conditional logic to determine whether menu prices should align with the lowest local prices or exceed them based on the context.

### 11. Final DataFrame
A comprehensive dataframe was created, showcasing:
1. Menu items of Village the Soul of India.
2. Suggested real-time pricing (considering competitor pricing, weather, and rush hours).
3. Original prices from the Yelp menu.

This structured approach ensured a detailed competitive analysis and data-driven insights for dynamic pricing strategies.
