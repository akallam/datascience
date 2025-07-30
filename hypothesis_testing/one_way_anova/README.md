# Introduction to ANOVA Test

This repository contains a Jupyter notebook (`one_way_anova.ipynb`) that demonstrates how to perform a one-way ANOVA (Analysis of Variance) test using Python.

## What is ANOVA?

ANOVA (Analysis of Variance) is a statistical test used to determine if there are any statistically significant differences between the means of three or more independent (unrelated) groups on a continuous dependent variable.

**Key Concepts:**

  * **Null Hypothesis ($H\_0$):** States that there is no significant difference between the means of the groups being compared.
  * **Alternative Hypothesis ($H\_A$):** States that at least one group mean is significantly different from the others.
  * **F-statistic:** The test statistic calculated in ANOVA, which compares the variance between group means to the variance within the groups.
  * **P-value:** The probability of observing the data (or more extreme data) if the null hypothesis were true. A small p-value (typically \< 0.05) leads to the rejection of the null hypothesis.
  * **Post-hoc tests:** If the ANOVA reveals a significant difference, post-hoc tests (e.g., Tukey's HSD, Bonferroni correction) are used to determine which specific group pairs differ significantly.

## Source Data
The analysis uses the `stack_overflow.feather` dataset. This dataset is sourced from DataCamp and is typically available as part of their courses on hypothesis testing or data analysis. 
It contains information related to Stack Overflow developers, including their compensation and job satisfaction levels.
To obtain the dataset, you would typically access it through a DataCamp course or platform that provides it.
## Notebook contents
The `one_way_anova.ipynb` notebook performs the following steps:

1. **Library Imports and Data Loading:** Imports pandas, pinguoin, seaborn, and matplotlib.pyplot and load dataset `stack_overflow.feather`.
2. **Data Exploration:**
   - Identify independent variable `job_stat` and dependent variable `converted_comp`
   - Examine `job_stat` distribution
   - Visualize `converted_comp` distribution across different `job_stat` categories.
3. **Perform Anova Test:**
   Apply a one-way ANOVA test to determine if there's a statistically significant difference in mean compensation based on job satisfaction.
4. **Perform Post-Hoc Tests:**
   If the ANOVA result indicates a significant difference, it then conducts pairwise comparisons between job satisfaction groups using Bonferroni correction to pinpoint which specific groups differ in their mean compensation.

## How to Run This File

To run the `one_way_anova.ipynb` notebook, follow these steps:

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/akallam/datascience.git
    cd datascience/hypothesis_testing/one_way_anova
    ```
2.  **Ensure you have the dataset:**
    Place the stack_overflow.feather file in a `../../data/` directory within your cloned repository, or modify the data loading path in the notebook to match your file's location.
3.  **Install Required Libraries:**
    The notebook uses `pandas`, `pingouin`, `seaborn`, and `matplotlib`. Install them using pip:

    ```bash
    pip install pandas pingouin seaborn matplotlib
    ```
4.  **Launch Jupyter Notebook:**
    Navigate to the directory containing `one_way_anova.ipynb` in your terminal or command prompt and run:

    ```bash
    jupyter notebook
    ```

6.  **Open and Run the Notebook:**
    Your web browser will open, showing the Jupyter interface. Click on `one_way_anova.ipynb` to open it. You can then run the cells sequentially by clicking "Run" or using `Shift + Enter`.
