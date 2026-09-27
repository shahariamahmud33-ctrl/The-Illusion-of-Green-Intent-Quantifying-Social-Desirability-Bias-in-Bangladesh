# The Illusion of Green Intent: Quantifying Social Desirability Bias in Bangladesh

An empirical research project investigating the **Intention-Behavior Gap** in sustainable purchasing decisions within Bangladesh. By employing the **Item Count Technique (List Experiment)**, this study mathematically neutralizes **Social Desirability Bias (SDB)** to deliver bias-adjusted behavioral conversion rates for Business Intelligence (BI) and green supply chain demand forecasting.

## 📌 Table of Contents

* [Executive Summary](#-executive-summary)

* [Key Findings](#-key-findings)

* [Methodology & Experimental Design](#-methodology--experimental-design)

* [Mathematical Framework](#-mathematical-framework)

* [Dataset & Variables](#-dataset--variables)

* [Repository Structure](#-repository-structure)

* [Replication & Usage](#-replication--usage)

* [Authors & Citation](#-authors--citation)

## 📊 Executive Summary

The transition toward a green economy is critical for Bangladesh's macroeconomic stability. While consumer self-reporting suggests a high willingness to buy eco-friendly products, actual purchasing behavior remains constrained by price premiums and skepticism.

This research highlights that traditional direct surveying suffers from severe **Social Desirability Bias (SDB)**. Consumers experience psychological pressure to report eco-conscious choices, leading to over-inflated intent metrics. Basing production forecasts and supply chain allocations on these direct metrics causes severe oversupply and financial misallocation.

## 🚀 Key Findings

| **Metric** | **Direct Self-Reporting** | **Item Count Technique (True Behavior)** | **Gap / Bias Inflation** | 
| **Conversion Rate** | **79.2%** | **24.7%** | **-54.5% Drop-off** | 

* **Direct Self-Reporting:** 79.2% ($95/120$) of respondents explicitly claim to make conscious green purchases.

* **List Experiment (Indirect):** True behavioral conversion rate drops to **24.7%**.

* **SDB Inflation Deficit:** A massive **54.5%** gap exists between stated intention and actual behavior.

* **Commercial Takeaway:** FMCG and retail companies must implement an empirical **bias discount rate** into their Business Intelligence (BI) models to prevent phantom demand forecasting.

## 🧪 Methodology & Experimental Design

To bypass psychological pressure without directly confronting respondents, an indirect survey technique called the **Item Count Technique (List Experiment)** was implemented on a sample size of $N = 120$.

The sample was randomly divided into two mutually exclusive cohorts:

### 1. Control Group ($n_c$)

Respondents were asked only for the total count (number) of statements that applied to them from a list of four innocuous shopping habits:

1. I always check the expiry date before buying groceries.

2. I compare prices between different brands before purchasing.

3. I usually make a shopping list before going to the store.

4. I prefer buying household items in bulk to save money.

### 2. Treatment Group ($n_t$)

Respondents were given the same four innocuous items plus a fifth sensitive green-purchasing statement:
5\. *I try to avoid plastic packed products, even for a pricier alternative.*

## 📐 Mathematical Framework

The true prevalence of sensitive green behavior is isolated by evaluating the difference in means between the Treatment group score ($\bar{x}_t$) and the Control group score ($\bar{x}_c$).

$$
\text{True Prevalence} = \bar{x}_t - \bar{x}_c = 2.705 - 2.458 = 0.247 \quad (24.7\%)
$$

### Statistical Testing (Welch's t-test)

To evaluate difference robustness across groups with unequal variances, Welch's t-test was applied:

$$
t = \frac{\bar{x}_t - \bar{x}_c}{\sqrt{\frac{\sigma_t^2}{n_t} + \frac{\sigma_c^2}{n_c}}}
$$

Degrees of Freedom ($df$) were approximated via the Welch–Satterthwaite equation:

$$
df = \frac{\left( \frac{\sigma_t^2}{n_t} + \frac{\sigma_c^2}{n_c} \right)^2}{\frac{\left( \sigma_t^2 / n_t \right)^2}{n_t - 1} + \frac{\left( \sigma_c^2 / n_c \right)^2}{n_c - 1}}
$$

#### Experimental Parameters:

* **Control Group Mean (**$\bar{x}_c$**):** $2.458 \quad (\sigma_c \approx 0.85)$

* **Treatment Group Mean (**$\bar{x}_t$**):** $2.705 \quad (\sigma_t \approx 0.98)$

* **t-statistic:** $t = 1.048$

* **p-value:** $p = 0.297$

> **Note on Sample Size:** While the $54.5\%$ gap provides actionable guidance for commercial forecasting, the $p$-value ($p > 0.05$) indicates that expanding the sample size ($N > 400$) is recommended in future iterations for academic hypothesis validation.

## 📁 Dataset & Variables

The collected dataset ($N=120$) captures urban and semi-urban demographic and behavioral indicators:

* **Demographics:** Age, Gender, Occupation, Estimated Household Income.

* **Perceived Commercial Barriers:** Price premiums, product availability, brand skepticism.

* **Direct Intent Flag:** Binary response on prior 6-month green purchases.

* **Item Count Tally:** Integer count of affirmative statements for Control and Treatment groups.

## 📂 Repository Structure

```
.
├── data/
│   ├── raw_survey_responses.csv     # Anonymized primary survey data (N=120)
│   └── processed_cohorts.csv        # Split Control & Treatment data
├── notebooks/
│   ├── 01_direct_reporting_analysis.ipynb
│   ├── 02_list_experiment_welch_ttest.ipynb
│   └── 03_visualization_generator.py
├── paper/
│   └── IEEE_Conference_Template.pdf # Full research manuscript
├── src/
│   ├── statistical_tests.py         # Welch's t-test & SDB calculator scripts
│   └── bi_discount_model.py         # Sample algorithm for BI demand adjustment
├── README.md
└── requirements.txt

```

## 🛠️ Replication & Usage

### Prerequisites

* Python 3.8+

* Jupyter Notebook / Lab

### Installation

1. Clone this repository:

   ```
   git clone https://github.com/your-username/green-intent-sdb-bangladesh.git
   cd green-intent-sdb-bangladesh
   
   ```

2. Install dependencies:

   ```
   pip install -r requirements.txt
   
   ```

### Running Statistical Analysis

Run the Welch's t-test calculation and calculate the SDB inflation gap:

```
python src/statistical_tests.py

```

## ✍️ Authors & Citation

**Ishtiak Mortuza**

Department of Computer Science and Engineering, Southeast University, Dhaka, Bangladesh

📧 `2023100000155@seu.edu.bd`

**Samia Afrin**

Department of Computer Science and Engineering, Southeast University, Dhaka, Bangladesh

📧 `2024200000005@seu.edu.bd`

**Shaharia Mahmud**

Department of Computer Science and Engineering, Southeast University, Dhaka, Bangladesh

📧 `2024100000113@seu.edu.bd`

## 📄 License

This project and dataset are distributed under the [MIT License](LICENSE).
