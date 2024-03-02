# Association

# Association Rules Book Dataset

## Overview
This dataset contains information about book purchases by customers. It includes various categories of books such as ChildBks, YouthBks, CookBks, DoItYBks, RefBks, ArtBks, GeogBks, ItalCook, ItalAtlas, ItalArt, and Florence.

## Instructions
1. **Support and Confidence Variation**:
    - Experiment with different values of support and confidence to observe the change in the number of rules generated. 
2. **Minimum Length in Apriori Algorithm**:
    - Explore changing the minimum length parameter in the Apriori algorithm to influence the generated rules.
3. **Visualization of Rules**:
    - Visualize the obtained rules using various plots.

## Dataset
- The dataset contains 2000 rows and 11 columns.

## Installation
```bash
!pip install mlxtend
import pandas as pd
from mlxtend.frequent_patterns import apriori, fpgrowth, association_rules

# Load the dataset
book = pd.read_csv('book.csv')

# Explore the dataset
print(book.head())
print(book.shape)

# Apply Apriori algorithm
frequent_itemsets_ap = apriori(book, min_support=0.1, use_colnames=True, verbose=1)

# Apply FpGrowth algorithm
frequent_itemsets_fp = fpgrowth(book, min_support=0.1, use_colnames=True, verbose=1)

# Generate association rules
rules_ap = association_rules(frequent_itemsets_ap, metric="confidence", min_threshold=0.4)
rules_fp = association_rules(frequent_itemsets_fp, metric="confidence", min_threshold=0.4)

# Visualize rules
# Add code for visualizing rules using different plots
import seaborn as sns
import matplotlib.pyplot as plt

# Heatmap for Confidence Metric
sns.heatmap(pivot, annot=True)
plt.title('Heat Map - For Confidence Metric')
plt.yticks(rotation=0)
plt.xticks(rotation=90)

# Heatmap for Lift Metric
sns.heatmap(pivot, annot=True)
plt.title('Heat Map - For Lift Metric')
plt.yticks(rotation=0)
plt.xticks(rotation=90)
This readme file outlines the steps to explore the Association Rules Book Dataset, experiment with different parameters, and visualize the generated rules. You can further enhance it by adding detailed descriptions of the algorithms used, insights gained from the rules, and additional visualizations.
