# User Churn and Activity Metrics Analysis

## Project Description

This project is dedicated to a comprehensive analysis of user data to find the key factors that affect churn. It also aims to monitor user activity using these main metrics:
* DAU (Daily Active Users)
* WAU (Weekly Active Users)
* MAU (Monthly Active Users)

**Main stages of the project:**

* Collecting data on user activity and characteristics by parsing a webpage. 
* Cleaning and transforming data for analysis, including combining datasets, processing dates, and removing outliers. 
* Visualizing key activity metrics (DAU, WAU, MAU) and identifying user behavior patterns. 
* Conducting a cohort analysis to evaluate user retention. 
* Calculating and visualizing the Churn Rate for each game separately. 
* Developing and implementing a machine learning model to predict churn. 
* Identifying the most important factors that contribute to churn, to help develop effective retention strategies.

  

## Cohort Analysis

A cohort is a group of users who started using a product (or had their first interaction) in the same defined period (in this project, one month).

1. Cohort Formation: Users are grouped by the month of their first activity (cohort_month). This allows you to track the behavior of that specific group over time. 
2. Tracking Retention: After the cohorts are formed, we analyze what part of these users stay active in the next months. This is shown with two heatmaps that present: 
    * The number of active users in each cohort (absolute values). 
    * The percentage of user retention in the periods after their first activity.
3. Identifying Trends: Cohort analysis helps to discover how the long-term retention of different user groups changes. For example, you can see if newer cohorts have better or worse retention rates than older ones.



## Churn Rate Analysis by Game

1.  **Calculating Activity Metrics**: For each user, we determine the date of their first and last activity, as well as the total duration of their "life" in the product.
2.  **Defining Churn**: A user is considered "churned" if two conditions are met:
    * Their last activity was more than 7 days ago. 
    * They were active in the game for at least 7 days (this helps to filter out users who just tried the game and didn't come back, separating them from those who were engaged but later left).
3.  **Calculating the Churn Rate**: The churn percentage is calculated for each game by dividing the number of "churned" users by the total number of unique users in that game.
4.  **Visualization**: The results are shown as a bar chart, which allows you to clearly compare the churn rates between the games.



## A Model that Determines the Impact of Metrics on Customer Churn

1.  Feature Creation: The model uses the following user characteristics:
    * `age` (age)
    * `language` (language)
    * `has_older_device_model` (presence of an old device)
    * `activity_variety` (variety of game actions)
    * `n_days_active` (total number of active days)
2.  Model Training: The Random Forest Classifier algorithm is used for the analysis. It is trained on the prepared data to predict churn.
3.  Identifying Key Factors: After training, the model allows us to evaluate the importance of each feature. The results are shown on a graph, which clearly demonstrates which factors have the biggest impact.

**Key Takeaway from the Model:**
The most important factors that influence churn are the number of active days and the player's age. In contrast, language, device model, and variety of actions have a much smaller impact.
