# Simply-Business-Dissertation
This is the second project of my dissertation, which is related to the insurance industry.

The aim of this project is to use NLP to deeply analyse the Financial Ombudsman Decisions (FOS) decision data and consumer
complaints, extracting valuable insights to identify common patterns, reasons, and trends in customer
complaints. We also want to build binary classification models to predict the FOS decision. We hope the outcome can help Simply Business 
improve their product and customer satisfaction so that can reduce future disputes.

Public Data Source: https://www.financial-ombudsman.org.uk/decisions-case-studies/ombudsman-decisions

**Description of Files:**
1. *project.ipynb*: contains all codes with explanation for this project.
2. *scrape.py*: download the metadata (and PDFs) of the Financial Ombudsman Decisions.
3. *data_to_eda.csv.zip*: a zip file includes the processed data after NLP extraction and before EDA.
4. *data_2023_2024.csv.zip*: an example dataframe includes what we extracted from PDFs. (we did not upload all years' data since they are too large)

## The structure of my codes (project.ipynb)
### Packages and Load Metadata
- install packages and load downloaded CSV data iteratively
### Data Cleaning and Preparation by Natural Language Processing 
This part of code is related to the section 2 in my report.

The key points are:
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
This part of code is related to the section 3 in my report.

The key points are:
- Correlation Analysis
  1. Among Categorical Variables (Cramér's V coefficient heatmap)
  2. Between Categorical and Numerical Variables (ANOVA table)
- Differences in FOS Considerations for Upheld and Not upheld:
  - What actions lead to an successful claim(Upheld)/unsuccessful claim(Not Upheld) with the FOS? (Word cloud plot)
- Company Analysis (put this into the Appendix in our report)
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
This part of code is related to the section 4 in my report.

The key things we did:
- Remove Irrelevant Variables
- Separate Feature and Target Variables
- Use TF-IDF to convert Text into Numbers (keyword counting)
- One-hot Encoding for Categorical Variables
- Standardization for Numerical Variables
### Predictive Modelling
This part of code is related to the section 5&6 in my report. I explained why I selected and how to use them in the report.

I also checked the distribution of the target variable **decision**.
The models we fit are:
- Logistics Regression
- Random Forest (recommend this finally)
- XGBoost
- Ensemble Model
