# T-Test for Independent Samples
This repository contains a Jupyter Notebook (`independent_samples_t_test.ipynb`) that performs a hypothesis test to investigate the relationship between shipment weight and on-time delivery status.

## Problem Statement

While trying to determine why some shipments are late, this analysis explores whether the weight of shipments that were on time is less than the weight of shipments that were late.

## Hypothesis Test Details

This notebook conducts a two-sample t-test for the difference in means.

### Null Hypothesis (Ho)

The mean weight of shipments that weren't late is the same as the mean weight of shipments that were late.

### Alternative Hypothesis ($Ha)

The mean weight of shipments that weren't late is less than the mean weight of shipments that were late.

### Significance Level (alpha)

The chosen significance level for this test is alpha = 0.05.

## Dataset

The analysis uses the `late_shipments.feather` dataset. This dataset is sourced from DataCamp and is typically available as part of their courses on hypothesis testing or data analysis. It contains information about various shipments, including their weight and whether they were delivered late.

To obtain the dataset, you would typically access it through a DataCamp course or platform that provides it.


## Notebook Contents

The `independent_samples_t_test.ipynb` notebook performs the following steps:

1.  **Library Imports and Data Loading**: Imports `pandas`, `numpy`, and `scipy.stats.t`, and loads the `late_shipments.feather` dataset.
2.  **Data Preparation and Descriptive Statistics**:
      * Groups the data by the `late` column.
      * Calculates the mean `weight_kilograms` for both on-time and late shipments.
      * Calculates the standard deviation of `weight_kilograms` for both groups.
      * Determines the number of observations (sample size) for each group.
      * Computes the numerator (difference in means) and the denominator (standard error of the difference) for the t-statistic formula.
3.  **T-statistic and Degrees of Freedom Calculation**:
      * Calculates the t-statistic using the derived numerator and denominator.
      * Determines the degrees of freedom for the t-test.
4.  **P-value Calculation**:
      * Calculates the p-value using the cumulative distribution function (`t.cdf`) from `scipy.stats` for a one-tailed (left-tailed) test.
5.  **Hypothesis Test Conclusion**:
      * Compares the calculated p-value to the significance level (alpha).
      * Prints a conclusion indicating whether to "Reject Null Hypothesis" or "Failed to reject null hypothesis".

## How to Run the Notebook

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/akallam/datascience.git
    cd datascience/hypothesis_testing/independent_samples_t_test
    ```
2.  **Ensure you have the dataset**: Place the `late_shipments.feather` file in a `../../data/` directory within your cloned repository, or modify the data loading path in the notebook to match your file's location.
3.  **Install dependencies**:
    Ensure you have the following libraries installed:
    ```bash
    pip install pandas numpy scipy jupyter
    ```
4.  **Launch Jupyter Notebook**:
    ```bash
    jupyter notebook
    ```
5.  **Open the notebook**: Navigate to `independent_samples_t_test.ipynb` in the Jupyter interface and open it.
6.  **Run the cells**: Execute the cells sequentially to perform the analysis.

## Results

Based on the provided notebook's execution, the p-value obtained was approximately 0.0084. Since this p-value is less than the significance level of 0.05, the null hypothesis is rejected. This provides statistical evidence that the mean weight of on-time shipments is less than the mean weight of late shipments.

-----