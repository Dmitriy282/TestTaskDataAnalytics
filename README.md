# TestTaskDataAnalytics


This task requires conducting an Exploratory Data Analysis (EDA), which involves examining data, identifying patterns, and providing key findings. Here's a step-by-step guide on how to approach this task:

▌Task Execution Steps

▍1. Import Necessary Libraries and Load Data

We will use the Pandas and Matplotlib libraries for working with data and creating graphs.
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
%matplotlib inline
```

Load data from a file:

```
df = pd.read_csv('path_to_your_file.csv')
```

▍2. Explore Data Structure

Let's look at the first rows of the data and check the data types in each column:
# View the first 5 rows
```
df.head()
```

# Check data types
```
df.info()
```
▍3. Data Statistics

Calculate the main statistical characteristics of numerical columns:
# Basic statistics
```
df.describe()
```

▍4. Visual Data Analysis

Create graphs for numerical variables:
# Histogram for likes_count
```
hashtags[:20].plot.barh(title='Top 20 Most Frequent Hashtags')
plt.xlabel("Кількість згадувань")
plt.ylabel("Хештег")
plt.show()
```
# The same for other numerical columns


▍5. Textual Information Analysis

Analyze text columns such as text_original. Find the most frequent words and hashtags:
```
def extract_hashtags(text):
    return re.findall(r'#\w+', str(text)) # Convert to string to handle non-string data
hashtags_list = df['text_original'].apply(extract_hashtags).explode()

hashtags_list = hashtags_list.dropna()
```
▍6. Correlation Analysis

Calculate the correlation matrix for numerical columns:
```
corr = df[['likes_count', 'shares_count', 'comments_count', 'views_count']].corr()
```

Display the correlation matrix:
```
sns.heatmap(corr, annot=True)
plt.show()
```

▍7. Report Preparation

Prepare a report that includes the following elements:

•   Description of the EDA process.
•   Key findings and conclusions.
•   Graphs and tables illustrating the results.
•   Code used for the analysis.

Example Report Structure:

Report

Introduction

•   Brief description of the analysis goal.
•   Description of the initial data.

EDA Process

•   Descriptions of the steps taken to examine the data.
•   Methods and tools used.

Results

•   Tables with statistical characteristics.
•   Graphs showing the data distribution.
•   Conclusions regarding correlations and trends.

Conclusion

•   Summary of the main results.
•   Recommendations for further research.

Appendices

•   Code used for analysis.
