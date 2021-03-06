# Used Cars Market Price Estimator: Project overview

# ![](/Data_files/100198028_2.jpg)


- Created a model that predicts the cars prices in the market (MAE - 15K) to help Buyers,Sellers,Investors satisfy the concern of how much does a car
cost in the Egyptian market considering it's features
- Scraped over than 12000 Ads from www.contactcars.com using python and selenium 
- Cleaned and Analyzed data to gain insights about the market.
- Engineerd features from the text of each Ad description & The Additional features of the cars (Interior Features,Exterior Features,Multimedia Features,Safety Features) to gain more insights about each car
- Applied several models(Linear regression,Decision tree,Random Forest) to reach the best model

# Code and Resources Used

**Python Version:** 3.7

**Main Packages:** Pandas,Numpy,scikit-learn,Matplotlib,Seaborn,BeautifulSoup,Selenium

# Project stages:

1. Getting Used Cars data (Scraping data)
2. Data Cleaning
3. Features Engineering
4. Data Anlaysis
5. Applying Machine Learning Model

# Data Scraping:

I have scraped the following features from www.contactcars.com website:

- Mobile_number
- Model_name
- SubModel_name
- Car_condition
- Kilometers_crossed
- Car_price
- Seller_City
- Model_year
- Body_type
- Transmission_type
- Motor_capacity
- Car_color
- Waranty_condition
- Car_paint
- Ad_post_date
- Interior_Features
- Exterior_Features
- Multimedia_Features
- Safety_Features


# Data Cleaning:

- Ammended columns data types         
- Fixed null values
- Dropped unnecessary columns

# Features Engineering:

Inorder to enhance the model performance i Featured Engineered the following features from (Interior Features,Exterior Features,Multimedia Features,Safety Features) columns:

- Panorama_roof
- Traction_Control
- Touch_screen
- Side_Airbags
- car_key	
- Sun_Roof
- Rear_view_camera
- Cruise_Control
- Rear_parking_sensors
- Leather_Seats
- Bluetooth
- Air_Bags_Passenger
- Anti_Lock_Braking_System_ABS
- USB
- Power_mirror
- Aux
- Air_Bags_For_Driver
- Electronic_window
- Analoge_Air_Condition

Featured Engineered the following features from the Text of each car's description:
- Car_paint_final(Extracted from the description and the ad options wether the car is still with it's factory paint or not)
- Accident(Wether the car had an accident or not)
- Payment_option(Cash or Installments)

From the Seller's city & Ad post Date columns:
- Area
- Governorate
- week_day
- Month
- Payment_option


# Outliers Handling:
- Removed main outliers from Kilometers and Car prices and rare car models
- Created a function that groups cars that are similar in Model,Submodel name,Model year,Motor capacity and checks for any price outliers among them and if an outlier exist it will replace it with the median of these cars, as slong as the car didn't have an accident or any similar event.

# EDA analysis:
I have conducted
1. Univariate analysis
2. Bivariate analysis
3. Multivariate analysis

Insights Examples:

Below is a distribution if the Model years in the market
# ![](/Data_files/Years.png)
This is a representation of the -ve correlation between Kilometers crossed and the car prices
# ![](/Data_files/Kilometers_vs_car_prices.png)
The distribution of car models in the market
# ![](/Data_files/Cars_models.png)

# Model Building:

- I selected specific features to use in training the model.
- I converted the categorical features into binary format using Labdel encoder as it generated the best results.
- I used a Logisitic Regression Model, Decision Tree Regressor Model & Random Forest Regressor Model
- My best results was generated from Random Forest Regressor Model with (MAE - 15K)
