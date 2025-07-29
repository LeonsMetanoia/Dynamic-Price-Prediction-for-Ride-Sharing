# Dynamic-Price-Prediction-for-Ride-Sharing

🚕 Dynamic Price Prediction for Ride-Sharing App
This project aims to build a machine learning model to predict the dynamic price of a ride in a ride-sharing platform based on various factors such as demand, time, location, and user behavior.

📌 Problem Statement
In ride-sharing apps, prices often fluctuate due to dynamic factors like rider/driver availability, time of day, and demand surges. This project focuses on predicting ride costs using historical and real-time features to improve pricing strategies and provide cost transparency.


🧪 Model Comparison
The following models were trained and compared for performance:

Linear Regression

Random Forest Regressor

XGBoost Regressor

Decision Tree

Support Vector Regressor (SVR)

Gradient Boosting

Evaluation metrics used:

Mean Absolute Error (MAE)

Root Mean Squared Error (RMSE)

R² Score


📁 Dataset Description
The dataset used for this project is dynamic_pricing.csv, which contains historical ride information from a ride-sharing app. The dataset initially consisted of 10 raw features:

🔹 Raw Dataset Columns (Before Feature Engineering)
Number_of_Riders: Total number of ride requests in a given time period and area.

Number_of_Drivers: Number of drivers available during that same period.

Location_Category: Type of area where the ride originated (Urban or Suburban).

Customer_Loyalty_Status: Customer loyalty tier (e.g., Regular, Silver).

Number_of_Past_Rides: Total number of rides completed by the user.

Average_Ratings: Average driver rating provided by the customer.

Time_of_Booking: Time slot when the booking was made (Morning, Evening, Night).

Vehicle_Type: Type of vehicle selected (Standard, Premium).

Expected_Ride_Duration: Estimated duration of the ride in minutes.

Historical_Cost_of_Ride: Historical ride cost for similar routes and conditions.

⚙️ Feature Engineering Steps
To improve prediction performance, the following transformations and new features were introduced:

Surge_Multiplier
→ Calculated as Number_of_Riders / Number_of_Drivers, representing demand-supply ratio.

Is_Peak
→ Binary feature indicating whether the ride occurs during peak hours (Evening/Night = 1).

Distance_KM
→ Estimated distance using a constant average city speed:
Distance_KM = Expected_Ride_Duration × 0.6 (assuming 0.6 km/min = 36 km/h).

Duration_Segment
→ Segmenting rides into time-based categories:

Short (≤ 60 min)

Medium (61–120 min)

Long (> 120 min)
Then label-encoded into numeric values.

One-Hot Encoding
→ Applied to categorical columns:

Location_Category → Location_Category_Urban, Location_Category_Suburban

Customer_Loyalty_Status → Customer_Loyalty_Status_Regular, Customer_Loyalty_Status_Silver

Time_of_Booking → Time_of_Booking_Morning, Time_of_Booking_Evening, Time_of_Booking_Night

Vehicle_Type → Vehicle_Type_Premium

🎯 Target variable: Historical_Cost_of_Ride


