# Energy Consumption Modelling

This repository contains a complete pipeline for the analysis and predictive modeling of energy consumption based on environmental variables, occupancy, equipment use, and time variables. The objective is to predict energy consumption and analyze the factors that most affect it, using linear regression and machine learning models.

## Dataset Description

The dataset includes variables such as:

- **Temperature**: Ambient temperature (°C)
- **Humidity**: Relative humidity (%)
- **SquareFootage**: Area of ​​the space (ft²)
- **Occupancy**: Number of people
- **HVACUsage**: Air conditioning usage (0/1)
- **LightingUsage**: Lighting usage (0/1)
- **DayOfWeek**: Day of the week (1=Monday, ..., 7=Sunday)
- **Holiday**: Holiday (0/1)
- **Hour**: Time of day (0-23)
- **Day**: Day of the month
- **Month**: Month of the year
- **WeekendLabel**: 0=Weekday, 1=Weekend (calculated automatically)
- **TimePeriodLabel**: 0=Afternoon, 1=Evening, 2=Morning, 3=Night (automatically calculated)
- **EnergyConsumption**: Energy consumption (kWh) - target variable

## Modeling pipeline

- Exploratory data review and analysis (EDA)
- Handling missing and duplicate values
- Automatic encoding of temporal variables (WeekendLabel, TimePeriodLabel)
- Scaling of numerical features with `StandardScaler`
- Model training and comparison:
- Linear regression
- Ridge regression
- Random Forest
- XGBoost
- Automatic selection of the best model by R²
- Visualization of residuals, comparison of actual vs. predicted values, and variable importance
- Saving the model and scaler for deployment
- GUI

## Prediction with interactive interface

Includes a Jupyter interface (ipywidgets) to enter input data and predict energy consumption. The pipeline internally calculates the derived variables (`WeekendLabel`, `TimePeriodLabel`) to ensure full consistency with the trained model.

## Getting Started

1. Clone this repository:
   ```bash
   git clone https://github.com/CatalinaNTU/EnergyConsumption.git
   cd EnergyConsumption
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the notebooks or scripts**
- Train and save the model + scaler
- Use the GUI file to test predictions with new data

## Requirements

- Python 3.8+
- pandas, numpy, scikit-learn, matplotlib, seaborn, xgboost, ipywidgets, joblib
  
## Data Source

The dataset used in this project is available on Kaggle. Refer to the [Kaggle notebook](https://www.kaggle.com/datasets/mrsimple07/energy-consumption-prediction/data) for direct data links and additional context.

## Notes

- The scaler used during training must be saved and loaded for correct predictions.
- Derived variables are automatically calculated from user input.

## Contributing

Contributions and suggestions are welcome. Please open an issue or submit a pull request.

## Contact

For questions or collaboration, please contact [CatalinaNTU](https://github.com/CatalinaNTU).

