# Paired T-Test
This repository contains a Jupyter Notebook (`paired_t_test.ipynb`) that performs a hypothesis test to investigate the relationship between votes percentage for republican candidates in 2008 and 2012.

## Problem Statement

This analysis explores whether the percentage of Republican candidate votes in 2008 was less than in 2012.

## Hypothesis Test Details

This notebook conducts a paired t-test for the difference in vote percentage.

### Null Hypothesis (Ho)

The percentage of republican candidate votes in 2008 is the same as the percentage of votes in 2012.

### Alternative Hypothesis (Ha)

The percentage of republican candidate votes in 2008 is less than the percentage of votes in 2012.

### Significance Level (alpha)

The chosen significance level for this test is alpha = 0.05.

## Dataset

The analysis uses the dataset from [Harvard](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/VOQCHQ). 
While the dataset `countypres_2000-2024.csv` contains county-level returns for presidential elections from 2000 through 2024, only data for 2008 and 2012 was considered, cleaning other data using pandas.

## Notebook Contents

The `paired_t_test.ipynb` notebook performs the following steps:

1.  **Library Imports and Setting significance level**: Imports `pandas`, `pingouin` and load `countypres_2000-2024.csv` dataset.
2.  **Data Cleaning and Preparation**
      * Filter the DataFrame to include only Republican candidate votes for the years 2008 and 2012.
      * Drop columns that are not relevant for the analysis, such as `state`, `county_fips`, `office`, `candidate`, `party`, `version`, and `mode`.
      * Create a new column called `votes_percent` by dividing `candidatevotes` by `totalvotes`.
3.  **Reshape the DataFrame**
      * Pivot the DataFrame so that `state_po` and `county_name` form the index, `year` becomes the columns, and `votes_percent` are the values.
      * Rename the year columns (2008 and 2012) to `percent_08` and `percent_12` for clarity.
4.  **Perform Paired t-test**
      * Execute a paired t-test using `pingouin.ttest` with percent_08 as x, percent_12 as y, paired=True, and alternative='less'.
5.  **Result Interpretation**
      * Compare the calculated p-value from paired t-test to the significance level (alpha).
      * Prints a conclusion indicating whether to "Reject Null Hypothesis" or "Failed to reject null hypothesis".

## How to Run the Notebook

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/akallam/datascience.git
    cd datascience/hypothesis_testing/paired_t_test
    ```
2.  **Ensure you have the dataset**: Place the `countypres_2000-2024.csv` file in a `../../data/` directory within your cloned repository, or modify the data loading path in the notebook to match your file's location.
3.  **Install dependencies**:
    Ensure you have the following libraries installed:
    ```bash
    pip install pandas pingouin
    ```
4.  **Launch Jupyter Notebook**:
    ```bash
    jupyter notebook
    ```
5.  **Open the notebook**: Navigate to `paired_t_test.ipynb` in the Jupyter interface and open it.
6.  **Run the cells**: Execute the cells sequentially to perform the analysis.

## Results

Based on the provided notebook's execution, the p-value obtained was approximately 0.00000. Since this p-value is less than the significance level of 0.05, the null hypothesis is rejected. This provides statistically significant evidence to support the claim that the percentage of Republican candidate votes in 2008 was less than the percentage of votes in 2012.

-----
