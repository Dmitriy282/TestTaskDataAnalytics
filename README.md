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
plt.figure(figsize=(10, 6))
plt.hist(df['likes_count'], bins=10)
plt.xlabel('Likes Count')
plt.ylabel('Frequency')
plt.title('Distribution of Likes Count')
plt.grid(True)
plt.show()

# The same for other numerical columns


▍5. Textual Information Analysis

Analyze text columns such as text_original and text_additional. Find the most frequent words and hashtags:
def extract_hashtags(text):
    return re.findall(r'#\w+', text)
