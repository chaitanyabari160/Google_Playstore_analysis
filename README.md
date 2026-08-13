# Google Play Store Data Analysis

## 1. Project Overview

This project focuses on **Exploratory Data Analysis (EDA) of Google Play Store applications**. The objective is to clean, transform, analyze, and visualize app-related data to understand patterns in **ratings, reviews, installs, categories, prices, genres, and other app characteristics**.

The dataset contains **10,357 records and 13 columns**.

The project demonstrates the complete data analysis workflow, starting from data cleaning and preprocessing to exploratory analysis and visualization.

---

## 2. Dataset

The dataset contains information about Google Play Store applications.

### Main Columns

* **App** – Name of the application
* **Category** – Application category
* **Rating** – User rating
* **Reviews** – Number of reviews
* **Size** – Application size
* **Installs** – Number of installations
* **Type** – Free or Paid application
* **Price** – Application price
* **Content Rating** – Target audience
* **Genres** – Application genre
* **Last Updated** – Date of the latest update
* **Current Ver** – Current application version
* **Android Ver** – Minimum Android version required

These columns are present in the project dataset.

---

## 3. Objectives

The main objectives of this project are:

1. Understand the structure of the Google Play Store dataset.
2. Identify and handle missing values.
3. Convert columns into appropriate data types.
4. Clean numerical columns such as **Reviews, Installs, and Price**.
5. Analyze app categories and genres.
6. Study the distribution of app ratings.
7. Analyze the relationship between reviews, ratings, and installs.
8. Compare free and paid applications.
9. Analyze content ratings and application characteristics.
10. Generate meaningful insights through data visualization.

---

## 4. Data Cleaning

Several preprocessing operations were performed before analysis.

### Missing Value Analysis

Missing values were identified using `isnull().sum()`.

Initially, missing values were found in columns such as:

* Rating
* Type
* Content Rating
* Current Ver
* Android Ver

The project also shows that **Current Ver** contained a large number of missing values.

### Handling Missing Values

Missing ratings were replaced using the mean rating:

```python
df['Rating'] = df['Rating'].fillna(df['Rating'].mean())
```

Missing current-version values were handled using:

```python
df['Current Ver'].fillna('Unknown')
```

### Data Type Conversion

Several columns initially had an `object` data type, including **Reviews, Installs, Price, and Last Updated**.

The project converted the **Last Updated** column to datetime:

```python
df['Last Updated'] = pd.to_datetime(df['Last Updated'])
```

After preprocessing, numerical columns such as **Reviews, Installs, and Price** were converted into appropriate numerical formats.

### Cleaning Installs

The `+` and `,` characters were removed from the `Installs` column:

```python
df['Installs'] = (
    df['Installs']
    .str.replace("+", "", regex=False)
    .str.replace(",", "", regex=False)
)
```

### Removing Unnecessary Column

The `Current Ver` column was removed at one stage of preprocessing:

```python
df = df.drop(['Current Ver'], axis=1)
```

---

## 5. Exploratory Data Analysis

EDA was performed to understand the distribution and relationships between different variables.

### Analysis Performed

* Distribution of app ratings
* App count by category
* Installation analysis
* Review analysis
* Free vs Paid applications
* Price analysis
* Content rating analysis
* Genre analysis
* Relationship between ratings and reviews
* Relationship between reviews and installs
* Analysis of application updates

The project also examines numerical variables such as **Rating, Reviews, Installs, and Price** for further analysis.

### Visualizations

The analysis uses visualizations to identify patterns and trends, including:

* Bar charts
* Histograms
* Distribution plots
* Scatter plots
* Box plots
* Correlation analysis

---

## 6. Key Insights

Based strictly on the analysis performed in the project, the major areas of insight are:

* Google Play Store applications are distributed across multiple categories and genres.
* User ratings provide an important measure of application performance.
* Reviews and installs can be used to understand application popularity.
* The dataset contains both **free and paid applications**.
* Applications target different **content-rating groups**, including Everyone, Teen, Everyone 10+, Mature 17+, and Adults only 18+.
* Data cleaning is important because several important columns originally contained string-formatted numerical values.
* Missing-value treatment significantly improves the dataset's readiness for analysis.

> **Note:** The uploaded notebook does not provide enough clearly retrievable output to safely state exact rankings such as "the most installed app" or "the highest-rated category," so those values should not be added without verifying the corresponding analysis output.

---

## 7. Technologies Used

### Programming Language

* Python

### Libraries

* **Pandas** – Data manipulation and cleaning
* **NumPy** – Numerical operations
* **Matplotlib** – Data visualization
* **Seaborn** – Statistical visualization

### Environment

* Jupyter Notebook

The uploaded file is a Jupyter Notebook exported as HTML, as indicated by its Jupyter-generated HTML structure.

---

## 8. Project Structure

```text
Google-Play-Store-Analysis/
│
├── README.md
│
├── data/
│   └── googleplaystore.csv
│
├── notebooks/
│   └── GP!.ipynb
│
├── visualizations/
│   ├── category_analysis.png
│   ├── rating_distribution.png
│   ├── installs_analysis.png
│   └── reviews_analysis.png
│
└── requirements.txt
```

### Workflow

```text
Dataset
   ↓
Data Loading
   ↓
Data Understanding
   ↓
Missing Value Analysis
   ↓
Data Cleaning
   ↓
Data Type Conversion
   ↓
Exploratory Data Analysis
   ↓
Data Visualization
   ↓
Key Insights
   ↓
Conclusion
```

## Conclusion

This project demonstrates a complete **data analysis and EDA workflow using Python**. It covers data cleaning, missing-value handling, type conversion, numerical transformation, exploratory analysis, and visualization of Google Play Store application data.

The project is suitable for demonstrating practical skills in **Python, Pandas, NumPy, Matplotlib, Seaborn, data cleaning, and exploratory data analysis**.
