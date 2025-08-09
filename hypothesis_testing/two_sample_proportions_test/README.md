# Two Sample Proportion Tests
A two-sample proportion test is a statistical method used to determine if there's a significant difference between the proportions of a certain characteristic in two independent populations.
This repository contains Jupyter notebooks that demonstrates how to perform a proportion tests between two groups using `proportions_ztest` from `statsmodels.stats.proportion`.

**Key Concepts:**

  * **Null Hypothesis ($H\_0$):** The null hypothesis assumes that there is no difference between the proportions of two populations ($p\_a$ = $p\_b$)

  * **Alternative Hypothesis ($H\_A$):** The alternate hypothesis suggests that there is significant difference between the proportions ($p\_a$ ≠ $p\_b$, $p\_a$ < $p\_b$, or $p\_a$ > $p\_b$)
  * **Z-Test:** The two-sample proportion test often uses a z-test, which is appropriate when sample size are large enough and the data follows an approximate normal distribution.
  * **P-value:** The probability of observing the data (or more extreme data) if the null hypothesis were true. A small p-value (typically \< 0.05) leads to the rejection of the null hypothesis.

## Source Data
The analysis uses the `stack_overflow.feather` and `late_shipments.feather` datasets. These datasets are sourced from DataCamp and is typically available as part of their courses on hypothesis testing or data analysis. 
To obtain these dataset, you would typically access it through a DataCamp course or platform that provides it.
## Notebook contents
The `late_shipment_vs_freight_cost_group.ipynb` and `proportion_of_hobbyist.ipynb` notebook performs the following steps:

1. **Library Imports and Data Loading:** Imports pandas, numpy, and proportions_ztest, and load dataset.
   - set significance level `alpha` to 0.05
3. **Data Exploration:**
   - Examine groups in interest using value_counts.
   - Get required data to perform proportions_ztest.
     - `count`: Number of success for each group
     - `nobs`: Total number of observations for each group  
4. **Perform Two Sample Proportion Tests:**
   Apply `proportions_ztest` specifying the type of test (`alternative`) argument. This returns `z-statistic` and a `p-value`
5. **Intrepreting p-value:**
  Compare the p-value to the significance level (`alpha`). If the p-value is less than or equal to the significance level, reject the null hypothesis.
## How to Run This File

To run the these notebooks, please follow these steps:

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/akallam/datascience.git
    cd datascience/hypothesis_testing/two_sample_proportions_test
    ```
2.  **Ensure you have the dataset:**
    Place the `stack_overflow.feather` and `late_shipments.feather` files in a `../../data/` directory within your cloned repository, or modify the data loading path in the notebooks to match your file's location.
3.  **Install Required Libraries:**
    The notebook uses `numpy`, `pandas`, `proportions_ztest`, `seaborn`, and `matplotlib`. Install them using pip:

    ```bash
    pip install numpy pandas statsmodels seaborn matplotlib
    ```
4.  **Launch Jupyter Notebook:**
    Navigate to the directory containings notebooks in your terminal or command prompt and run:

    ```bash
    jupyter notebook
    ```

6.  **Open and Run the Notebook:**
    Your web browser will open, showing the Jupyter interface. Click on any notebook to open it. You can then run the cells sequentially by clicking "Run" or using `Shift + Enter`.
