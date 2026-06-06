# BITS Pilani (M.Tech AIML)
## Introduction to Statistical Methods (S2-25_AIMLCLZC418)
### Assignment 1 Solutions — AIML Section 3

**Student Name:** Sumanth N  
**Student ID:** 2025AC05403  
**Section:** Section 3  
**Date:** June 5, 2026  

---

### **Question 1: Descriptive Statistics [2.5 Marks]**

**Problem Statement:**  
Temperatures (in °C) measured at noon for 11 consecutive days are:  
`31, 29, 27, 34, 32, 28, 33, 29, 35, 26, 30`  

1. Compute the mean, median, variance, range, and Q1, Q3 for this group.  
2. Use the IQR method to identify the outliers in the dataset.  

---

#### **Solution 1(i): Step-by-Step Calculations**

**Step 1: Sort the data in ascending order**  
To compute the median and quartiles, we line up the 11 data points from lowest to highest:  
Sorted Data: [26, 27, 28, 29, 29, 30, 31, 32, 33, 34, 35]  
Total number of observations (n) = 11.

---

**Step 2: Compute the Mean (X_bar)**  
The mean is the sum of all observations divided by the total count (n):  
Mean (X_bar) = (Sum of all X_i) / n  
Sum of all X_i = 26 + 27 + 28 + 29 + 29 + 30 + 31 + 32 + 33 + 34 + 35 = 334  
Mean (X_bar) = 334 / 11 = 30.3636 °C  

---

**Step 3: Compute the Median (Q2 / 50th Percentile)**  
Since the number of observations n = 11 is odd, the median is the middle value located at the position index (n + 1) / 2:  
Median Position = (11 + 1) / 2 = 6th position  
Looking at our sorted data, the 6th value is:  
Median = 30.0 °C  

---

**Step 4: Compute the Range**  
The range is the difference between the maximum and minimum values in the dataset:  
Range = Maximum - Minimum = 35 - 26 = 9.0 °C  

---

**Step 5: Compute the Quartiles (Q1 and Q3)**  
We compute the quartiles using the Tukey Method (median-excluding method) which is the standard method presented in the course slides:
*   **Lower Quartile (Q1):** The median of the lower half of the data (excluding the overall median value 30).  
    Lower Half = {26, 27, 28, 29, 29} (5 values)  
    The median of these 5 values is the 3rd value:  
    Q1 = 28.0 °C  
*   **Upper Quartile (Q3):** The median of the upper half of the data (excluding the overall median value 30).  
    Upper Half = {31, 32, 33, 34, 35} (5 values)  
    The median of these 5 values is the 3rd value:  
    Q3 = 33.0 °C  

*(Optional Reference - Standard Interpolation Method):*  
*If using standard software percentile interpolation:*  
*   *Position of Q1 = (n + 1) / 4 = 12 / 4 = 3rd value, giving Q1 = 28.0 °C.*  
*   *Position of Q3 = 3 * (n + 1) / 4 = 9th value, giving Q3 = 33.0 °C.*  
*(Both methods yield Q1 = 28.0 °C and Q3 = 33.0 °C for this dataset).*

---

**Step 6: Compute the Variance**  
We compute both the Sample Variance (s^2) and Population Variance (sigma^2) for completeness:  
1.  **Deviations from the Mean (X_bar = 30.3636):**  
    We calculate the deviation (X_i - X_bar) and squared deviation (X_i - X_bar)^2 for each day:
    
    | Day (i) | Temp X_i | Deviation (X_i - X_bar) | Squared Deviation (X_i - X_bar)^2 |
    | :---: | :---: | :---: | :---: |
    | 1 | 26 | -4.3636 | 19.0413 |
    | 2 | 27 | -3.3636 | 11.3140 |
    | 3 | 28 | -2.3636 | 5.5868 |
    | 4 | 29 | -1.3636 | 1.8595 |
    | 5 | 29 | -1.3636 | 1.8595 |
    | 6 | 30 | -0.3636 | 0.1322 |
    | 7 | 31 | +0.6364 | 0.4050 |
    | 8 | 32 | +1.6364 | 2.6777 |
    | 9 | 33 | +2.6364 | 6.9504 |
    | 10 | 34 | +3.6364 | 13.2231 |
    | 11 | 35 | +4.6364 | 21.4959 |
    | **Sum** | **334** | **0.0000** | **SS = 84.5455** |

2.  **Sum of Squares (SS):**  
    SS = Sum of (X_i - X_bar)^2 = 84.5455  
3.  **Sample Variance (s^2):**  
    Used when treating these 11 days as a sample:  
    s^2 = SS / (n - 1) = 84.5455 / 10 = 8.4545 °C^2  
4.  **Population Variance (sigma^2):**  
    Used if treating this 11-day period as the entire population:  
    sigma^2 = SS / n = 84.5455 / 11 = 7.6860 °C^2  

---

#### **Solution 1(ii): Outlier Identification using the IQR Method**

**Step 1: Calculate the Interquartile Range (IQR)**  
IQR = Q3 - Q1 = 33.0 - 28.0 = 5.0 °C  

**Step 2: Calculate the Outlier Fences**  
Using the 1.5 * IQR rule:  
*   **Lower Fence:**  
    Lower Fence = Q1 - 1.5 * IQR = 28.0 - 1.5 * 5.0 = 28.0 - 7.5 = 20.5 °C  
*   **Upper Fence:**  
    Upper Fence = Q3 + 1.5 * IQR = 33.0 + 1.5 * 5.0 = 33.0 + 7.5 = 40.5 °C  

**Step 3: Check for Outliers**  
A data point X is considered a potential outlier if:  
X < Lower Fence (20.5 °C) or X > Upper Fence (40.5 °C)  

Comparing each sorted day temperature against the fences:  
Minimum value 26 >= 20.5 and Maximum value 35 <= 40.5  
All data points sit comfortably within the range [20.5, 40.5].  

**Conclusion:**  
There are **no outliers** in this temperature dataset.

---
---

### **Question 2: Probability Addition Rule [2.5 Marks]**

**Problem Statement:**  
In a class of 40 students, there are 18 boys and 22 girls. Out of the boys, 7 participate in sports and 6 scored an ‘A’ grade, with 3 boys involved in both. Among the girls, 9 participate in sports, 8 scored an ‘A’ grade, and 4 girls did both. If a student is picked at random, what is the probability the student is either involved in sports or scored an ‘A’ grade?  

---

#### **Solution 2: Step-by-Step Calculation**

Let the total class size N = 40.  
Let us define the events:  
*   **S:** The student participates in sports.  
*   **A:** The student scored an 'A' grade.  
*   **S and A:** The student participates in sports and scored an 'A' grade (involved in both).  

We wish to find P(S or A), which is the probability that the student is either involved in sports or scored an 'A' grade.  

**Step 1: Calculate the Counts for Each Event**  
We aggregate the boy and girl statistics to find class-wide counts:  
*   **Total Sports Participants, N(S):**  
    N(S) = Boys(S) + Girls(S) = 7 + 9 = 16 students  
*   **Total A-Grade Students, N(A):**  
    N(A) = Boys(A) + Girls(A) = 6 + 8 = 14 students  
*   **Total Students in Both, N(S and A):**  
    N(S and A) = Boys(Both) + Girls(Both) = 3 + 4 = 7 students  

---

**Step 2: Compute Individual Probabilities**  
Since a student is selected at random out of the total class (N = 40):  
*   P(S) = N(S) / N = 16 / 40 = 0.40  
*   P(A) = N(A) / N = 14 / 40 = 0.35  
*   P(S and A) = N(S and A) / N = 7 / 40 = 0.175  

---

**Step 3: Apply the Addition Rule of Probability**  
To find the probability of the union of the two non-mutually exclusive events:  
P(S or A) = P(S) + P(A) - P(S and A)  
P(S or A) = 16 / 40 + 14 / 40 - 7 / 40  
P(S or A) = (16 + 14 - 7) / 40 = 23 / 40  
P(S or A) = 0.575 (or 57.5%)  

**Conclusion:**  
The probability that a randomly picked student is either involved in sports or scored an 'A' grade is **23/40 or 0.575 (57.5%)**.

---
---

### **Question 3: Naïve Bayes Classifier [5 Marks]**

**Problem Statement:**  
A mental health organization is developing a simple machine learning model to help counsellors identify whether a person may have depression based on common symptoms. The organization decides to use the Naïve Bayes Classifier for prediction.  

| Person | Trouble Sleeping | Low Energy | Anxiety | Has Depression |
| :---: | :---: | :---: | :---: | :---: |
| A1 | Yes | Yes | Yes | Yes |
| A2 | No | Yes | No | No |
| A3 | Yes | No | Yes | Yes |
| A4 | No | No | No | No |

A new patient visits the counsellor with the following symptoms:  
*   Trouble Sleeping = **Yes**  
*   Low Energy = **No**  
*   Anxiety = **Yes**  

---

#### **Solution 3(a): Target Variable**
The target variable (also called the class label) is the variable we want to predict.  
*   **Target Variable (Y):** `Has Depression` (takes binary values: `Yes` or `No`).

---

#### **Solution 3(b): Prior Probabilities**
Total number of historical instances (N) = 4.
*   **Prior Probability of Depression = Yes (P(Yes)):**  
    P(Yes) = (Count of Depression = Yes) / Total Count = 2 / 4 = 0.5  
*   **Prior Probability of Depression = No (P(No)):**  
    P(No) = (Count of Depression = No) / Total Count = 2 / 4 = 0.5  

---

#### **Solution 3(c): Conditional Probabilities**
We compute the conditional probabilities for the features given that `Has Depression = Yes` (based on instances A1 and A3):
1.  **P(Trouble Sleeping = Yes | Depression = Yes):**  
    Out of the 2 people with depression (A1, A3), both have Trouble Sleeping = Yes.  
    P(Trouble Sleeping = Yes | Yes) = 2 / 2 = 1.0  
2.  **P(Low Energy = No | Depression = Yes):**  
    Out of the 2 people with depression (A1, A3), A3 has Low Energy = No, while A1 has Low Energy = Yes.  
    P(Low Energy = No | Yes) = 1 / 2 = 0.5  
3.  **P(Anxiety = Yes | Depression = Yes):**  
    Out of the 2 people with depression (A1, A3), both have Anxiety = Yes.  
    P(Anxiety = Yes | Yes) = 2 / 2 = 1.0  

---

#### **Solution 3(d): Compute Naïve Bayes Probability for New Patient**

Let the new patient's symptoms be X = (Trouble Sleeping = Yes, Low Energy = No, Anxiety = Yes).  
The Naïve Bayes classifier assumes features are conditionally independent given the class label.

##### **Method 1: Standard Maximum Likelihood Estimation (MLE) - No Smoothing**

1.  **Likelihood and Score for Class Yes:**  
    Likelihood(Yes) = P(Trouble Sleeping = Yes | Yes) * P(Low Energy = No | Yes) * P(Anxiety = Yes | Yes)  
    Likelihood(Yes) = 1.0 * 0.5 * 1.0 = 0.50  
    Score(Yes) = Likelihood(Yes) * P(Yes) = 0.50 * 0.5 = 0.25  

2.  **Likelihood and Score for Class No:**  
    Let us find the conditional probabilities given Depression = No (based on instances A2 and A4):  
    *   P(Trouble Sleeping = Yes | No) = 0 / 2 = 0.0 (Neither A2 nor A4 have Trouble Sleeping = Yes).  
    *   P(Low Energy = No | No) = 1 / 2 = 0.5 (A4 has Low Energy = No).  
    *   P(Anxiety = Yes | No) = 0 / 2 = 0.0 (Neither A2 nor A4 have Anxiety = Yes).  
    
    Likelihood(No) = 0.0 * 0.5 * 0.0 = 0.00  
    Score(No) = Likelihood(No) * P(No) = 0.00 * 0.5 = 0.00  

3.  **Posterior Probabilities Calculation (Normalizing):**  
    The total evidence probability P(X) in the denominator is:  
    P(X) = Score(Yes) + Score(No) = 0.25 + 0.00 = 0.25  
    
    P(Yes | symptoms) = Score(Yes) / P(X) = 0.25 / 0.25 = 1.0 (100%)  
    P(No | symptoms) = Score(No) / P(X) = 0.00 / 0.25 = 0.0 (0%)  

---

##### **Method 2: Laplace (Add-One) Smoothing (Alternative)**
*Since some conditional probabilities for class `No` are zero, Laplace smoothing is often used in practice to avoid zero probability issues.*  
For a binary feature (with k = 2 categories: Yes and No):  
P(Feature = value | Class) = (Count(Feature = value and Class) + 1) / (Count(Class) + 2)  

1.  **Smoothed Conditional Probabilities for Depression = Yes:**  
    *   P(Trouble Sleeping = Yes | Yes) = (2 + 1) / (2 + 2) = 3 / 4 = 0.75  
    *   P(Low Energy = No | Yes) = (1 + 1) / (2 + 2) = 2 / 4 = 0.50  
    *   P(Anxiety = Yes | Yes) = (2 + 1) / (2 + 2) = 3 / 4 = 0.75  
2.  **Smoothed Conditional Probabilities for Depression = No:**  
    *   P(Trouble Sleeping = Yes | No) = (0 + 1) / (2 + 2) = 1 / 4 = 0.25  
    *   P(Low Energy = No | No) = (1 + 1) / (2 + 2) = 2 / 4 = 0.50  
    *   P(Anxiety = Yes | No) = (0 + 1) / (2 + 2) = 1 / 4 = 0.25  
3.  **Smoothed Numerator Scores:**  
    *   Score(Yes) = (0.75 * 0.50 * 0.75) * P(Yes) = 0.28125 * 0.5 = 0.140625  
    *   Score(No) = (0.25 * 0.50 * 0.25) * P(No) = 0.03125 * 0.5 = 0.015625  
4.  **Smoothed Posterior Probabilities:**  
    *   P(Yes | symptoms) = Score(Yes) / (Score(Yes) + Score(No)) = 0.140625 / (0.140625 + 0.015625) = 0.140625 / 0.15625 = 0.90 (90%)  
    *   P(No | symptoms) = Score(No) / (Score(Yes) + Score(No)) = 0.015625 / (0.140625 + 0.015625) = 0.015625 / 0.15625 = 0.10 (10%)  

---

#### **Solution 3(e): Prediction & Decision**
Based on both calculation methods:
*   **Without Laplace Smoothing (MLE):** P(Depression = Yes | symptoms) = 1.0 > P(Depression = No | symptoms) = 0.0.  
*   **With Laplace Smoothing:** P(Depression = Yes | symptoms) = 0.90 > P(Depression = No | symptoms) = 0.10.  

Since the posterior probability for `Has Depression = Yes` is significantly larger than for `No` in both methods:  
*   **Prediction:** **The new patient is predicted to have depression (`Has Depression = Yes`).**  
*   **Justification:** The Naïve Bayes classification rule selects the class Y that maximizes the posterior probability (or numerator score). Since the score/probability for `Yes` is higher, we classify the patient as having depression.
