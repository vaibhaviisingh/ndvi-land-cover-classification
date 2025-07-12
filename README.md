# 🌿 NDVI-Based Land Cover Classification using Logistic Regression  
*A Machine Learning Project for the Summer Analytics 2025 Hackathon*

---

## 🏆 About the Hackathon

This project was developed for the **First Course Hackathon of Summer Analytics 2025**, hosted by:

- **Consulting & Analytics Club, IIT Guwahati** — a student-led initiative promoting data science and business analytics
- **GeeksforGeeks (GFG)** — one of India's largest computer science education platforms

The goal was to apply logistic regression to classify land cover types using NDVI (Normalized Difference Vegetation Index) data from satellite images.  
Participants competed for **GFG Premium memberships** and exclusive discounts.

---

## 🔍 Problem Statement

Classify land cover types — such as **Water**, **Impervious**, **Farm**, **Forest**, **Grass**, and **Orchard** — using **NDVI time-series satellite data** and **OpenStreetMap (OSM) labels**.

### What is NDVI?

NDVI (Normalized Difference Vegetation Index) is calculated using:

NDVI=NIR-RED/NIR+RED

- **NIR**: Near-Infrared reflectance  
- **RED**: Red reflectance  

It indicates the presence and health of vegetation in satellite images.

---

## ⚠️ Data Challenges

- **📉 Noise**: Cloud cover and imprecise OSM labels introduce noisy signals
- **🕳 Missing Data**: NDVI values are missing when clouds obscure satellite view
- **🔁 Temporal Variations**: Seasonal NDVI fluctuations require time-aware processing

> 🔒 The **training and test data used in the public leaderboard** contains noise.  
> 🧪 However, the **private leaderboard** (final evaluation) uses clean data to test model generalization.

---

## 📁 Dataset Structure

Each row in the dataset represents a geographic point and contains:

- `ID`: Unique identifier  
- `27 NDVI columns`: Labeled like `20150720_N`, `20150602_N`, etc.  
- `class`: Ground truth land cover label (only in training data)

Possible land cover classes:
•	water
•	impervious
•	farm
•	forest
•	grass
•	orchard


> ⚠️ **Note**: `hacktrain.csv` and `hacktest.csv` are not uploaded here due to competition restrictions.  
> 📌 Access the data from the [official hackathon page](https://www.kaggle.com/competitions/summer-analytics-mid-hackathon/overview).

---

## 🎯 Objective

Build a **multiclass Logistic Regression model** that can:
- Handle missing and noisy NDVI signals
- Learn seasonal vegetation trends
- Predict land cover type for unseen test data

---

## ⚙️ Tech Stack

| Tool / Library    | Purpose                         |
|-------------------|---------------------------------|
| Python (Google Colab) | Code execution environment   |
| Pandas / NumPy    | Data loading and transformation |
| Scikit-learn      | Imputation, scaling, model training |
| CSV               | Submission file format          |

---

## 📊 Evaluation Metric

Submissions were evaluated based on **accuracy score**:

| Leaderboard | Data | Purpose |
|-------------|------|---------|
| **Public (89%)** | Noisy test data | Immediate feedback |
| **Private (11%)** | Clean test data | Final leaderboard |

---

## 🚀 Workflow Summary

### 1. Load Data
- Read `hacktrain.csv` and `hacktest.csv`

### 2. Preprocess
- Fill missing NDVI values using `SimpleImputer` (mean strategy)
- Normalize features using `StandardScaler`

### 3. Train Model
- Logistic Regression (Multiclass, solver='lbfgs', max_iter=1000)

### 4. Predict & Submit
- Predict classes for test data
- Save results as `vaibhavisubmission.csv`

---

## 📄 Submission Format

Required format for submission:

```csv
ID,class
1,water
2,water
3,grass
4,impervious
```
...
🧠 Key Takeaways
```
•	Built an end-to-end classification pipeline under modeling constraints
•	Applied denoising, imputation, and feature engineering
•	Understood the real-world challenges of working with satellite imagery
•	Learned to build models that generalize across noisy and clean datasets
```

📂 Repository Contents
```
File	Description
NDVI(vaibhavi).ipynb	  Google Colab-compatible notebook with full pipeline
vaibhavisubmission.csv	  Final prediction file for Kaggle submission
README.md   	This file — complete project documentation
```

🧑‍💻 Author
```
Vaibhavi Singh Rathaur
Final Year B.Tech – Computer Science & Business Systems (CSBS)
Rajiv Gandhi Proudyogiki Vishwavidyalaya (RGPV), India
💻 Interests: Web Development, Data Science
🔗 https://www.linkedin.com/in/vaibhavisingh999894a/
🐙 https://github.com/vaibhaviisingh
```

🚀 How to Run
1. Clone this repository:
git clone https://github.com/yourusername/ndvi-land-cover-classification.git
2. Open notebook.ipynb in Google Colab
3. Upload hacktrain.csv and hacktest.csv from the competition
4. Run all cells to generate vaibhavisubmission.csv

🤝 Acknowledgments
•	Consulting & Analytics Club, IIT Guwahati – for organizing the hackathon and providing real-world satellite data
•	GeeksforGeeks (GFG) – for sponsoring and mentoring the competition
•	Kaggle – for hosting the leaderboard and submission system
•	Google Colab – for making development easy and accessible

