# IBM Data Science Capstone - SpaceX

## Introduction

![SpaceX Launch](https://camo.githubusercontent.com/9523424e56778424998ea8ca427a804c42d7a6d940fbcffc99d9b7d4b28df38b/68747470733a2f2f63662d636f75727365732d646174612e73332e75732e636c6f75642d6f626a6563742d73746f726167652e617070646f6d61696e2e636c6f75642f49424d446576656c6f706572536b696c6c734e6574776f726b2d445330373031454e2d536b696c6c734e6574776f726b2f6170692f496d616765732f6c616e64696e675f312e676966)

### Background
SpaceX, a pioneering company in the space industry, is dedicated to making space travel accessible and affordable for all. Through innovations such as the reusable first stage of its Falcon 9 rocket, SpaceX has reduced launch costs to $62 million per mission, significantly less than competitors who charge upwards of $165 million. The company's milestones include sending spacecraft to the International Space Station, deploying a satellite constellation for global internet access, and conducting manned space flights.

This project aims to predict whether the first stage of a Falcon 9 launch will successfully land, providing insights that can help estimate the cost of future missions. We will use public data and machine learning techniques to determine the likelihood of a successful rocket landing.

## Project Focus

The focus of this project includes:
- Analyzing how factors such as payload mass, launch site, number of flights, and orbit type influence the success of first-stage landings.
- Investigating the success rate of rocket landings over time.
- Identifying the most effective predictive model for determining landing success (binary classification).

## Executive Summary

This research explores the factors contributing to a successful Falcon 9 rocket landing. The methodologies used in the project include:

- **Data Collection:** Gathering launch data from SpaceX’s REST API and web scraping techniques.
- **Data Wrangling:** Creating a binary outcome variable to indicate whether a landing was successful or not.
- **Exploratory Data Analysis (EDA):** Visualizing the impact of factors such as payload mass, launch site, flight number, and time on landing success.
- **SQL Analysis:** Investigating payload ranges, success rates, and the correlation between launch outcomes.
- **Launch Site Exploration:** Analyzing success rates based on geographic locations of launch sites.
- **Model Building:** Building predictive models to estimate landing success using logistic regression, support vector machine (SVM), decision tree, and K-nearest neighbor (KNN).

## Results

### Exploratory Data Analysis (EDA)
- The success rate of landings has improved over time.
- The Kennedy Space Center (KSC) LC-39A has the highest landing success rate among all sites.
- Orbits such as ES-L1, GEO, HEO, and SSO show a 100% success rate.

### Visualization and Analysis
- Most launch sites are located near the equator and close to coastal regions.

### Predictive Analytics
- All models performed similarly, with the decision tree model showing a slight edge based on the `.best_score_` metric.

## Methodology

### Data Collection - API
1. Request launch data from the SpaceX API.
2. Decode the API response with `.json()` and convert it into a dataframe using `.json_normalize()`.
3. Gather additional launch details using custom functions.
4. Convert the gathered data into a dictionary and then a dataframe.
5. Filter the dataframe to only include Falcon 9 launches.
6. Handle missing values in the `Payload Mass` column by filling them with the mean.
7. Save the processed data to a CSV file.

### Data Collection - Web Scraping
1. Extract Falcon 9 launch data from Wikipedia using web scraping.
2. Parse the HTML response with BeautifulSoup.
3. Extract column names from the table headers and parse the HTML tables to collect relevant data.
4. Store the extracted data in a dictionary and then convert it to a dataframe.
5. Save the final dataframe to a CSV file.

### Data Wrangling
- Convert the launch outcomes into binary values, where 1 represents a successful landing and 0 represents a failure.

### Exploratory Data Analysis (EDA) with Visualization
- Create visualizations to analyze relationships and patterns in the data.

### EDA with SQL
- Use SQL queries to derive insights such as payload ranges, success rates, and launch outcomes.

### Maps with Folium
- Use maps to visualize the locations of launch sites and their proximity to geographical features.

### Dashboard with Plotly Dash
- Build a dashboard to display the following visualizations:
  - A pie chart showing the proportion of successful launches.
  - A scatter plot illustrating the relationship between payload mass and success rates by booster version.

## Predictive Analytics

1. Convert the `Class` column to a NumPy array.
2. Standardize the data using `StandardScaler`.
3. Split the dataset into training and testing sets using `train_test_split`.
4. Use `GridSearchCV` for hyperparameter tuning with 10-fold cross-validation.
5. Apply `GridSearchCV` to the following models:
   - Logistic Regression (`LogisticRegression()`),
   - Support Vector Machine (`SVC()`),
   - Decision Tree (`DecisionTreeClassifier()`),
   - K-Nearest Neighbor (`KNeighborsClassifier()`).
6. Calculate model accuracy using `.score()` on the test set.
7. Evaluate model performance using confusion matrices.
8. Identify the best-performing model using evaluation metrics like Jaccard Score, F1 Score, and Accuracy.

## Conclusion

- **Model Performance:** All models showed similar performance, with the decision tree model performing slightly better in terms of accuracy.
- **Equatorial Advantage:** Most launch sites are near the equator, providing a natural advantage for fuel efficiency.
- **Coastal Locations:** All launch sites are strategically located near the coast to allow safe ocean landings.
- **Launch Success Over Time:** The success rate of launches has increased over the years.
- **KSC LC-39A:** This site has the highest success rate and a 100% success rate for payloads under 5,500 kg.
- **Orbit Success Rates:** Orbits like ES-L1, GEO, HEO, and SSO show a 100% success rate.
- **Payload Mass and Success:** Higher payload mass tends to correlate with higher success rates across all launch sites.

## Contact Information
- **Name:** Lai Jien Weng
- **Email:** laijienweng@gmail.com
- **LinkedIn:** [LinkedIn Profile](https://www.linkedin.com/in/jienweng/)
