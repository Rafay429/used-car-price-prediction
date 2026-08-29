# Used Car Price Prediction 🚗

A Machine Learning project that predicts the price of used cars using
features such as mileage, model year, horsepower, engine capacity,
cylinders, brand, transmission, fuel type, and other car information.

The project uses a Random Forest Regressor with feature engineering,
frequency encoding, and One-Hot Encoding.

## 📊 Dataset

Dataset: `used_cars.csv`

The dataset contains information about used cars, including:

- Brand
- Model
- Model Year
- Mileage
- Fuel Type
- Transmission
- Exterior Color
- Interior Color
- Accident History
- Clean Title
- Engine Information
- Price

## 🔧 Data Preprocessing

The following preprocessing steps were performed:

- Checked dataset shape and data types
- Checked missing values
- Checked duplicate rows
- Filled missing categorical values
- Converted mileage from string to float
- Converted price from string to float
- Detected extreme price values
- Removed the top 5% extreme price outliers

The 95th percentile of price was used as the upper limit.

## ⚙️ Feature Engineering

New features were extracted from the `engine` column:

- Horsepower
- Engine Capacity
- Cylinders
- Turbo indicator

A new feature was also created from the transmission column:

- Automatic transmission indicator

Another feature was created:

- Car Age

### High Cardinality Encoding

The following high-cardinality categorical features were frequency encoded:

- Model
- Exterior Color
- Interior Color

### One-Hot Encoding

The following categorical features were One-Hot Encoded:

- Brand
- Fuel Type
- Transmission
- Accident
- Clean Title

## 🤖 Machine Learning Model

The project uses:

**Random Forest Regressor**

The preprocessing and model training were combined using a Scikit-Learn Pipeline and ColumnTransformer.

## 📈 Model Performance

After feature engineering and removing extreme price outliers:

- **R² Score:** 0.81
- **MAE:** $6,264.12
- **RMSE:** $9,757.87

### Results

| Metric | Result |
|---|---:|
| R² Score | 0.81 |
| MAE | $6,264.12 |
| RMSE | $9,757.87 |

An initial model achieved an R² score of approximately 0.08.
After feature engineering, it improved to approximately 0.12.
After treating extreme price outliers, the R² score increased to 0.81.

## 📊 Visualization

The project includes visualizations for:

- Price distribution
- Mileage vs Price
- Model Year vs Price
- Horsepower vs Price
- Brand vs Price
- Random Forest Feature Importance

### Feature Importance

The Random Forest model identified mileage as the most important feature,
followed by horsepower, car age, model year, and engine capacity.

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn

## 📁 Project Structure

```text
Used-Car-Price-Prediction/
│
├── used_cars.csv
├── used_car_price_prediction.ipynb
├── README.md
└── requirements.txt