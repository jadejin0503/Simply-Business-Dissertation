# Simply-Business-Dissertation
This is the second project of my dissertation, which is related to the data analysis of the insurance industry by using NLP and classification models. 

Files Description:
1. *project.ipynb*: contains all codes for this project.
2. *scrape.py*: download the metadata (and PDFs) of the Financial Ombudsman Decisions.
3. *data_to_eda.csv*: processed data after NLP extraction

## The structure of my codes (project.ipynb):
### Packages and Load Metadata
- install packages and load downloaded CSV data iteratively
### Data Cleaning and Preparation by Natural Language Processing
- Extract Information From PDF files several times
  - Merge data into a file with 6 years data from July 11, 2018, to July 11, 2024, and reprocess the text data
- Extract Insurance Product Type 
- Data Cleaning
- Extract Complaint Reason
- Sentiment Analysis
- Date Processing and Obtain Dispute Duration
- More Data Cleaning
  - save the processed data into a CSV file *data_to_eda.csv* to avoid repetitive code execution to improve efficiency
### Explanatory Data Analysis
In this section, we examined the data type and missing values. Many visualizations with analysis are provided in the notebook.
- Correlation Analysis
  1. Among Categorical Variables (Cramér's V coefficient heatmap)
  2. Between Categorical and Numerical Variables (ANOVA table)
- Target Variable (decision) Analysis
  1. The distribution of **decision**
  2. What actions lead to an successful claim(Upheld)/unsuccessful claim(Not Upheld) with the FOS? (Word cloud plot)
- Company Analysis
  1. Summary Table for:
     - top 5 complaint companies
     - top 5 upheld rate companies
     - top 5 not upheld rate companies
- Product and Complaint Analysis
  1. Relevant variables' distributions by decision (Bar and line combination chart)
  2. The relation between insurance types and negative sentiment by decision (Stacked bar chart)
  3. Table showing the proportion of each complaint reason for every insurance type
  4. The distribution of insurance products across different dispute durations (Pie chart)
- Time-related Variable Analysis
  1. The distribution of time-related variables (Bar and line combination chart)
  2. Insurance product changes over the years (Line chart)
  3. Customer complaint sentiments over the years (Line chart)
### Feature Engineering
- Remove Irrelevant Variables
- Separate Feature and Target Variables
- Use TF-IDF to convert Text into Numbers (keyword counting)
- One-hot Encoding for Categorical Variables
- Standardization for Numerical Variables
### Predictive Modelling
- Logistics Regression
- Random Forest
- XGBoost
- Ensemble Model
