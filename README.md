# XGBoost-for-PCB-Reflow
PCB Reflow Oven Temperature Prediction
Project Overview
This project predicts optimal temperature settings for each zone of a reflow oven based on PCB characteristics. The model helps eliminate time-consuming trial-and-error approaches traditionally used in reflow profiling

Key Features
- Predicts temperatures for all 10 zones of a reflow oven
- Uses XGBoost regression models with hyperparameter optimization
- Advanced feature engineering focused on thermal properties
- Achieves high R² scores for accurate temperature predictions

The model uses PCB physical characteristics to predict optimal temperature settings:

Input Features
- PCB_Thickness_mm: Thickness of the PCB
- Board_Length_mm: Length of the PCB
- Board_Width_mm: Width of the PCB
- Copper_Weight_oz: Copper weight in ounces
- Component_Count: Total number of components
- 0201_Resistors: Count of 0201 size resistors
- 0402_Inductors: Count of 0402 size inductors
- Alum_Caps: Count of aluminum capacitors
- 0603_Caps: Count of 0603 size capacitors
- Connectors: Count of connectors
- Paste_Type: Type of solder paste used
- Conveyor_Speed_cm_per_min: Speed of the conveyor belt

Engineered Features
- Board_Area: Product of board length and width
- Thermal_Load: Product of component count and copper weight
- Area_to_Thickness: Ratio of board area to thickness
- Component_Density: Component count per unit area
- Thermal_Exposure: Product of conveyor speed and board length

Target Variables
- Zone_1_Temp_C through Zone_10_Temp_C: Optimal temperature for each zone

Model Architecture
- Algorithm: XGBoost regression with MultiOutputRegressor
- Preprocessing: StandardScaler for numerical features, OneHotEncoder for categorical features
- Hyperparameter Optimization: Optuna framework with 50 trials
- Evaluation Metrics: R², MAE, RMSE

Performance
The model achieves strong performance across all temperature zones:
- Average R²: 0.81 (81% of temperature variability explained)
- Average MAE: ±2.52°C (average absolute error)
- Average RMSE: 3.14°C (root mean squared error)
