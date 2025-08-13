# ♻ Waste Management and Recycling in India – Predictive Modeling

## 📌 Overview
This project predicts the **Recycling Rate (%)** for waste generated in Indian cities using environmental, infrastructural, and socio-economic factors.  
The dataset is simulated based on real-world waste management trends (2019–2023) and includes information about waste types, landfill details, municipal efficiency, and more.  

By using **feature engineering** and **machine learning**, this model helps:
- Optimize landfill usage
- Improve waste segregation policies
- Allocate resources efficiently
- Support sustainable urban development

---

## 📂 Dataset Description

**Columns:**
- `City/District` – Name of the Indian city or district
- `Waste Type` – Type of waste (Plastic, Organic, E-Waste, Construction, Hazardous)
- `Waste Generated (Tons/Day)` – Amount of waste generated per day
- `Recycling Rate (%)` – Percentage of waste recycled (**target variable**)
- `Population Density (People/km²)` – People per square kilometer
- `Municipal Efficiency Score (1-10)` – Effectiveness of municipal waste management
- `Disposal Method` – Landfill, Recycling, Incineration, Composting
- `Cost of Waste Management (₹/Ton)` – Cost per ton
- `Awareness Campaigns Count` – Number of awareness programs in the year
- `Landfill Name` – Name of landfill site
- `Landfill Location (Lat, Long)` – Geographic coordinates
- `Landfill Capacity (Tons)` – Total landfill capacity
- `Year` – Data entry year (2019–2023)

---

## 🛠 Methodology

### 1. Data Preprocessing
- Filled missing numeric values with **median**
- Filled missing categorical values with **mode**
- Extracted `Landfill Latitude` & `Landfill Longitude` from coordinates
- Converted `Year` to categorical for trend analysis

### 2. Feature Engineering
New features created:
- `Waste_per_Density` – Waste Generated per Population Density
- `Landfill_Utilization` – Waste Generated / Landfill Capacity
- `Efficiency_Awareness` – Municipal Efficiency × Awareness Campaigns
- `Cost_per_Ton_Generated` – Cost per ton of generated waste
- `Recycling_Landfill_Ratio` – Recycling rate vs landfill capacity
- `Landfill_Distance_to_Center` – Distance from India's centroid

### 3. Encoding
- **Target Encoding**: `Waste Type`, `Disposal Method`
- **One-Hot Encoding**: `City/District`, `Landfill Name`

### 4. Model
- **Random Forest Regressor**
- Robust to outliers & multicollinearity
- Captures non-linear patterns in data

---

## 📊 Results

| Metric   | Train Score | Test Score |
|----------|-------------|------------|
| R²       | 0.996       | 0.974      |
| RMSE     | 2.684       | 2.684      |

**Feature Importance Highlights:**
- Landfill Capacity
- Waste Generated
- Efficiency_Awareness
- Population Density

---

## 📦 Installation & Usage

```bash
# Clone repository
git clone https://github.com/shubham01s2/Waste-Management-and-Recycling-in-Indian-Cities.git
cd waste-management-predictor

# Install dependencies
pip install -r requirements.txt

# Run model training
python train_model.py

# Predict with saved model
python predict.py
