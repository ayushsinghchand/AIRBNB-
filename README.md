# 🏠 Airbnb Open Data — Exploratory Data Analysis & Preprocessing
 
A data cleaning and preprocessing pipeline built on the **Airbnb Open Dataset**, preparing raw listing data for downstream analysis or machine learning tasks.
 
---
 
## 📁 Project Structure
 
```
├── AIR_BNB_data.ipynb       # Main Jupyter Notebook
├── CSV_Cleaned_data.csv     # Output: Cleaned dataset
└── README.md
```
 
---
 
## 📌 Objectives
 
- Load and explore the raw Airbnb Open Dataset
- Drop irrelevant or low-quality columns
- Handle missing values and duplicate records
- Clean and standardize key features (`price`, `instant_bookable`, `host_identity_verified`)
- Export a clean CSV ready for further analysis or modeling
---
 
## 🛠️ Tech Stack
 
| Library | Purpose |
|---|---|
| `pandas` | Data manipulation & cleaning |
| `numpy` | Numerical operations |
| `matplotlib` | Visualization |
| `seaborn` | Statistical plots |
| `scikit-learn` | Preprocessing utilities |
 
---
 
## 🔄 Pipeline Overview
 
### 1. Data Loading
```python
data = pd.read_csv("/content/Airbnb_Open_Data.csv")
```
 
---
 
### 2. Column Selection
Retained **18 meaningful features** and dropped 8 low-signal columns:
 
**Kept:** `NAME`, `host id`, `host_identity_verified`, `host name`, `neighbourhood group`, `neighbourhood`, `lat`, `long`, `country`, `country code`, `instant_bookable`, `cancellation_policy`, `room type`, `Construction year`, `price`, `service fee`, `minimum nights`, `number of reviews`
 
**Dropped:** `id`, `reviews per month`, `review rate number`, `calculated host listings count`, `availability 365`, `house_rules`, `license`, `last review`
 
---
 
### 3. Deduplication
```python
data.drop_duplicates(inplace=True)
```
 
---
 
### 4. Null Handling
```python
data.dropna(inplace=True)
```
 
---
 
### 5. Feature Cleaning
 
- **`price`** — Stripped `$`, commas, and spaces → cast to `int`
- **`instant_bookable`** — Encoded as binary (`1` / `0`)
- **`host_identity_verified`** — Normalized to uppercase
---
 
### 6. Export
```python
data.to_csv("CSV_Cleaned_data.csv", index=False)
```
 
---
 
## 📊 Dataset
 
**Source:** [Airbnb Open Data — Kaggle](https://www.kaggle.com/datasets/arianazmoudeh/airbnbopendata)
 
The dataset contains NYC Airbnb listings with details on hosts, location, pricing, policies, and availability.
 
---

 
