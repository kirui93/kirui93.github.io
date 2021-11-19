# Uber Fare Prediction
## Objective
The objective of this project is to design an algorithm which will tell the fare to be charged for a passenger.
## Problem Statement
A fare calculator helps a customer in identifying the fare valid for the trip. 
They are often used by passengers who are new to a city or tourists to get an estimate of travel costs. 
You are provided with a dataset with features like fare amount, pickup and drop location, passenger count, and so on.

## Dataset

Here, you are provided with a train dataset with more than 5M observations. There are 8 columns in the dataset as follows:
  1. key
  2. fare_amount
  3. pickup_time
  4. pickup_longitude
  5. pickup_latitude
  6. dropoff_longitude
  7. dropoff_latitude
  8. passanger_count

## Steps

Inorder to generate the machine learning models, the following steps were taken on the dataset provided:
* Load a sample of the train dataset (we used only 200,000 observations because of the processor).
* Convert the pickup_time to a DateTime format.
* Check for the unusual values. For example, the pickup_longitude and latitude had some large values. Similarly, there was some negative fare amounts in the dataframe.
* Drop observations where the latitudes and longitudes are not in the decided ranges.
* Check for missing values and drop the rows with missing values.
* Extract days, weekdays, month and years from the datetime column.
* Calculate distance from the dropoff and pickup latitudes and longitudes.
* Drop observations where the distance is zero.

## Machine Learning Models

Since this is a regression problem, we only used two models :*Linear Regression* and *Random Forest Regression* models. 

To measure the performance of the models, we used the *Root Mean Squared Error*, which is defined as follows:
$$\sqrt{\sum_{i=1}^{n} \frac{(\hat{y}_i - y_i)^2}{n}}$$

Random Forest Regressor, with a RMSE of 3.85, performed better than Linear Regression (RMSE = 5.32) and hence we chose it as our final model.

## Next steps
To improve the performance of our models, we need to do the following:
1. Hyperparameter tuning
2. Feature tuning

Stay Tuned.
