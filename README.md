# Screen Time Analysis of Mobile App Usage Patterns

## Overview
This project analyzes screen time data to uncover patterns in mobile app usage. By leveraging data analysis techniques such as statistical methods, visualizations, and machine learning (including Logistic Regression), this study identifies key trends in user engagement. The goal is to provide insights that can help app developers, marketers, and stakeholders better understand how users interact with their mobile devices and applications.

## Features
- Analyze app usage patterns by examining screen time, app sessions, and usage frequency.
- Visualize app usage trends over time.
- Explore the relationship between notifications, app usage, and session lengths.
- Implement **Logistic Regression** to predict high and low app engagement based on notifications received.
- Generate insights for app developers to improve user experience based on real data.

## Dataset
The dataset used for this project, `Screentime - App Details Updated.csv`, was obtained from Kaggle. It includes the following columns:
- `Date`: The date when the data was recorded.
- `Usage`: Total time spent using the app (in minutes).
- `Notifications`: Number of notifications received from the app.
- `Times Opened`: Number of times the app was opened.
- `App`: The name of the app whose usage was recorded.

## Installation
1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/screen-time-analysis.git
    cd screen-time-analysis
    ```

2. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Launch the project:
    ```bash
    python analysis.py
    ```

## Usage
1. **Data Preprocessing**: The dataset is cleaned by removing missing values or filling them with appropriate substitutes. Null values are addressed to ensure accurate analysis.
2. **Data Visualization**: The app usage data is visualized through various charts, such as:
   - Bar charts to show app usage over time.
   - Scatter plots to explore relationships between notifications and usage.
   - Pie charts for the distribution of app openings.
3. **Logistic Regression**: A Logistic Regression model is used to predict whether an app is likely to receive a high or low number of notifications based on:
   - Date
   - Day of the week
   - Number of notifications
   - Month
   - Random noise to challenge the model’s predictive abilities

    The goal is to classify app notification levels (high vs. low) using these features.

## Example Visualizations
- **App Usage Over Time**:
    ```python
    figure = px.bar(data_frame=df, x="Date", y="Usage", color="App", title="App Usage Over Time")
    figure.show()
    ```

- **Relationship Between Notifications and Usage**:
    ```python
    figure = px.scatter(data_frame=df, x="Notifications", y="Usage", size="Notifications", trendline="ols", title="Notifications vs. Usage")
    figure.show()
    ```

## Logistic Regression
The project implements a Logistic Regression model to predict whether an app will receive high or low notifications based on various factors. This helps in understanding the relationship between notifications and user engagement. The steps include:

- **Feature Engineering**: Extract day of the week, month, and convert the date to ordinal values.
- **Scaling**: Features are scaled to improve model performance.
- **Model Training and Evaluation**: The Logistic Regression model is trained with cross-validation and hyperparameter tuning.
- **Evaluation**: The accuracy, confusion matrix, and classification report are used to evaluate model performance.
  

## Results
The analysis reveals that:
- Users engage more with a small subset of apps regularly, such as social media and entertainment.
- Peak usage times often occur in the mornings and evenings.
- There is a positive correlation between the number of notifications received and the time spent on an app.
- Logistic Regression successfully predicts high or low app engagement based on notification patterns, with an accuracy of over 80%.
