# Eniac Homepage A/B Test Analysis

This project details the A/B testing process conducted by Eniac to improve the click-through rate (CTR) of their homepage's primary call-to-action button. The analysis covers the experimental design, data exploration, and statistical significance testing to determine the most effective button variant.

---

## Table of Contents

* [Project Overview](#project-overview)
* [Experimental Design](#experimental-design)
* [Metrics](#metrics)
* [Hypotheses](#hypotheses)
* [Data and Analysis](#data-and-analysis)
* [Results](#results)
* [Winner Determination](#winner-determination)
* [How to Run the Analysis](#how-to-run-the-analysis)

---

## Project Overview

Eniac's current homepage "SHOP NOW" button has a low **click-through rate (CTR)** of approximately 2%. To improve user engagement and ultimately conversion, the UX team designed three new button variations based on user feedback and successful past ad campaigns. This A/B test aims to identify which button variant, including the original, performs best.

---

## Experimental Design

The experiment included four variants of the homepage button:

* **Version A:** White "SHOP NOW" (Original)
* **Version B:** Red "SHOP NOW"
* **Version C:** White "SEE DEALS"
* **Version D:** Red "SEE DEALS"

The test ran for **14 days**, from November 2, 2021, to November 16, 2021, to cover two full business cycles.

---

## Metrics

### Primary Metric (for statistical significance)

* **Click-Through Rate (CTR) for the homepage button:** Number of clicks on the button divided by the total number of visits to the page. This measures the initial ability of a website element to attract user interaction.

### Additional Metrics (for decision-making)

* **Drop-off rate for the linked page:** The percentage of visitors who start a conversion process but don't complete it. A lower rate indicates better user engagement after clicking the button.
* **Homepage-return rate for the category pages:** How often users return to the homepage after clicking the button. A lower return rate suggests users are finding relevant content on the linked page, indicating the button effectively leads them to desired information.

---

## Hypotheses

* **Null Hypothesis ($H_0$):** All versions of the button have the same click-through rate (CTR).
* **Alternative Hypothesis ($H_1$):** There is a difference in the click-through rate (CTR) for at least one of the different versions.

### Statistical Significance Threshold

A typical statistical significance level of $\alpha = 0.01$ (corresponding to a 90% confidence level) was chosen for the initial chi-square test.

### Minimum Detectable Effect (MDE)

The Minimum Detectable Effect was set to a **20% improvement** in CTR. This was determined to be the smallest increase in the conversion pipeline that would justify the cost of implementing a small website change.

---

## Data and Analysis

The Data Folder contains the raw data from the experiment. The `Eniac_AB_Test_Analysis.ipynb` Colab notebook guides through the following steps:

1.  **Data Loading and Exploration:**
    * Loading the dataset.
    * Calculating the CTR for each version.
    * Initial observations on the performance of each variant.
2.  **Chi-Square Test:**
    * Constructing a contingency table for clicks and no-clicks across all versions.
    * Performing a chi-square test using `scipy.stats.chi2_contingency` to determine if observed differences in CTR are statistically significant.
3.  **Post-Hoc Analysis with Bonferroni Adjustment:**
    * Since the initial chi-square test compares more than two variants, post-hoc tests are performed for each pair of variants.
    * The Bonferroni Adjustment is applied to the $\alpha$ level to mitigate the increased risk of Type I errors due to multiple comparisons.

---

## Results

*(This section will be populated with the key findings from your Colab notebook after you run the analysis. For example, you would include the p-value from the chi-square test and the results of the post-hoc comparisons.)*

---

## Winner Determination

Based on the statistical analysis of the CTR and considering the additional metrics (drop-off rate and homepage-return rate) where available, the final winner of the A/B test is determined.

---

## How to Run the Analysis

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YourGitHubUsername/Eniac_AB_Test_Analysis.git](https://github.com/YourGitHubUsername/Eniac_AB_Test_Analysis.git)
    ```
2.  **Navigate to the project directory:**
    ```bash
    cd Eniac_AB_Test_Analysis
    ```
3.  **Open the Colab notebook:**
    * Go to [Google Colab](https://colab.research.google.com/).
    * Click on "File" -> "Upload notebook" and select `Eniac_AB_Test_Analysis.ipynb` from your cloned repository. Alternatively, you can open it directly from GitHub by navigating to the notebook file and clicking the "Open in Colab" button.
4.  **Run all cells in the notebook:** Follow the instructions within the notebook to execute the code and see the analysis results.

---

## Files in this Repository

* `Eniac_AB_Test_Analysis.ipynb`: The Google Colab notebook containing all the Python code for data exploration, statistical tests, and analysis.
* `eniac_a.csv`,`eniac_b.csv`,`eniac_c.csv`,`eniac_d.csv`: The dataset containing the results of the A/B test for each version.
