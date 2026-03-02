# 🛌 Human Sleep Patterns & Stress: Inferential Analysis (Part 2)

## 📌 Project Overview

Following the analysis of REM sleep stages in Part 1, this project shifts focus to **Sleep Duration**. By applying inferential statistics to a 6-month longitudinal dataset from a wearable fitness tracker, we aim to determine the reliability of the user's sleep consistency. Specifically, we estimate the **proportion** of nights the user meets the healthy threshold of **7+ hours of sleep**.

---

### 🔗 Project Navigation
* **Previous Stage:** [← Part 1 - REM Sleep Analysis (Means)](./Path_To_Part1_Folder_Or_URL)
* **Current Stage:** Part 2 - Sleep Duration Analysis (Proportions)

---

## 📈 The Business Problem

Health experts generally agree that adults require at least **7 hours of sleep** per night for optimal cognitive function and emotional regulation. While a sample might show a certain percentage of "healthy" nights, we need to determine the **Confidence Interval** to understand where the true population proportion likely lies.

The goal is to provide a statistical range that identifies how often the friend actually achieves a healthy sleep duration, accounting for sampling error.

---

## 🛠️ Methodology & Approach

### 1. Data Processing

We analyzed 179 days of sleep data, categorizing each night as a "Success" (if sleep duration $> 7$ hours) or "Failure" (if sleep duration $\le 7$ hours).

### 2. Statistical Formula Used

Unlike Part 1 (which used means), this analysis uses the **Confidence Interval for Proportions**. The formula used to calculate the Margin of Error ($E$) is:

$$E = z \cdot \sqrt{\frac{\hat{p}(1-\hat{p})}{n}}$$

Where:

* $\hat{p}$ = Sample proportion (Successes / Total $n$)
* $z$ = Critical value based on the confidence level
* $n$ = Sample size

### 3. Execution Steps

* **Sample Size ($n$):** Calculated total observations using `COUNT`.
* **Success Count:** Identified nights with $> 7$ hours using `COUNTIF`.
* **Point Estimate ($\hat{p}$):** Calculated the raw percentage of healthy nights.
* **Interval Construction:** Developed intervals for both **95%** and **99%** confidence levels to compare precision vs. certainty.

---

## 📊 Results & Calculations

### Sample Statistics

| Metric | Value |
| --- | --- |
| **Total Sample Size ($n$)** | 179 |
| **Healthy Nights Count ($> 7$ hrs)** | 140 |
| **Sample Proportion ($\hat{p}$)** | **0.7821 (78.2%)** |

### Confidence Intervals

| Confidence Level | z-score | Margin of Error | Lower Bound | Upper Bound | Interval Width |
| --- | --- | --- | --- | --- | --- |
| **95%** | 1.96 | 0.0605 | 72.16% | 84.26% | 12.09% |
| **99%** | 2.576 | 0.0795 | 70.26% | 86.16% | 15.90% |

---

## 🧠 Insights & Conclusions

### 1. Precision vs. Certainty

* The **99% Confidence Interval** is wider (15.9%) than the 95% interval (12.1%). This illustrates the statistical trade-off: to be more certain that our range includes the true proportion, we must accept a wider, less precise range.

### 2. Performance Against Benchmarks

* We can say with **95% confidence** that the user sleeps more than 7 hours between **72.16% and 84.26%** of the time.
* Even in the "worst-case" scenario (the lower bound of the 99% CI), the user is still getting healthy sleep at least **70%** of the time.

### 3. Final Recommendations

* **Consistency Check:** While 78% is a strong majority, nearly 1 out of every 4 nights falls below the healthy threshold.
* **Contextual Analysis:** It is recommended to cross-reference the "failed" nights ($< 7$ hours) with the **REM Sleep** data from Part 1. If low duration correlates with the suppressed REM percentages ($< 20\%$) found previously, it confirms a systemic recovery issue.
* **Action Plan:** The user should investigate "Day of the Week" trends to see if sleep deprivation is concentrated on workdays vs. weekends to better stabilize their sleep schedule.

---


## 🎓 Project Credits
This analysis was developed as part of the **Applied Statistics for Data Analytics** course by **DeepLearning.AI** on Coursera. It focuses on using discrete distributions to solve predictive problems in media and entertainment.

---

## 👤 About the Author
**Ayushi Gajendra** 

*Data Analyst | Former EdTech Co-Founder*

* **7+ Years** of experience in business operations, strategic growth, and entrepreneurial leadership.
* I specialize in bridging the gap between raw data and **high-stakes business decisions**.
* My goal is to help organizations move beyond "gut feeling" to drive growth through evidence-based strategy.
