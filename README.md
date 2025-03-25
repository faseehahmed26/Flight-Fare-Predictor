# Flight Fare Predictor

![Python](https://img.shields.io/badge/Python-3.7+-blue)
![Framework](https://img.shields.io/badge/Framework-Flask-red)
![ML Library](https://img.shields.io/badge/ML_Library-Scikit_Learn-orange)
![R² Score](https://img.shields.io/badge/R²_Score-0.79-green)
![Deployment](https://img.shields.io/badge/Deployment-Heroku-purple)

A machine learning application that predicts domestic flight prices based on various parameters like departure date, airline, source, destination, and other factors.

![App Interface](https://github.com/faseehahmed26/Flight-Fare-Predictor/blob/main/static/css/prediction.png?raw=true)

## Features

- Predicts flight prices with ~80% accuracy
- Considers multiple factors affecting airfare
- Simple and intuitive web interface
- Provides instant predictions

## Technology Used

- **Machine Learning**: Random Forest Regression
- **Data Processing**: Pandas, NumPy, Scikit-learn
- **Hyperparameter Tuning**: RandomizedSearchCV
- **Visualization**: Matplotlib, Seaborn
- **Web Framework**: Flask
- **Deployment**: Heroku

## Model Development

The predictive model was developed through a comprehensive process:

1. **Data Preprocessing**:
   - Handling categorical variables using one-hot encoding
   - Converting date and time features into numerical format
   - Engineering duration features by extracting hours and minutes
   - Removing irrelevant information

2. **Feature Engineering**:
   - Extracted day and month from journey dates
   - Split departure and arrival times into hours and minutes
   - Created explicit features for flight duration
   - Encoded airline, source, and destination information

3. **Feature Selection**:
   - Used ExtraTreesRegressor to identify important features
   - Applied correlation analysis to understand feature relationships
   - Top predictors: total stops, journey day, and airline type

4. **Model Selection and Optimization**:
   - Tested multiple regression algorithms
   - Selected Random Forest Regressor based on performance
   - Optimized hyperparameters using RandomizedSearchCV
   - Best parameters: n_estimators=800, max_depth=30, min_samples_split=10

5. **Model Evaluation**:
   - R² Score: 0.797
   - Mean Absolute Error: 1,145 rupees
   - Root Mean Square Error: 2,011 rupees

## Installation and Usage

```bash
# Clone repository
git clone https://github.com/faseehahmed26/Flight-Fare-Predictor.git
cd Flight-Fare-Predictor

# Install requirements
pip install -r requirements.txt

# Run application
python app.py
```
Input Parameters

Airline: The airline providing the flight service
Source: Departure city
Destination: Arrival city
Departure Date: Date of departure
Stops: Number of layovers
Arrival Time: Scheduled arrival time
Departure Time: Scheduled departure time

Project Structure
├── Data_Train.xlsx      # Training dataset
├── Test_set.xlsx        # Testing dataset
├── app.py               # Flask application
├── flight_rf.pkl        # Serialized model
├── requirements.txt     # Dependencies
├── static/              # CSS and static files
├── templates/           # HTML templates
└── Flight Price Prediction.ipynb  # Main notebook
Future Improvements

Incorporate international flight data
Add more features like seat class and booking time
Implement time series analysis for seasonal trends
Create a mobile application version

License
This project is licensed under the MIT License.
