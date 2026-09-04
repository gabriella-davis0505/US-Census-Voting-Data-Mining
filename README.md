# US Census and Voting Data Mining

Data mining and visual analytics project completed in **Orange Data Mining**, using large-scale US census data and 2020 US Presidential election data.

The project explores demographic and socioeconomic patterns in income, develops classification models for income prediction, and combines census and election data to investigate geographic voting patterns across US states.

---

## Project Overview

This project was completed as part of an **MSc Data Science Data Mining module**.

The analysis uses **Orange**, a visual data-mining and machine-learning platform, to investigate several questions relating to income, demographics and voting behaviour.

The coursework covers five main areas:

1. data preprocessing and outlier analysis;
2. fairness and demographic differences in income;
3. classification and prediction of income;
4. demographic analysis of the 2020 US Presidential election; and
5. an independent investigation into marital status and income.

The project combines exploratory analysis, statistical testing, machine learning, clustering and geographic visualisation.

---

# Tools and Technologies

The main analytical work was completed using:

- **Orange Data Mining**
- CSV datasets
- visual workflow-based data preparation
- statistical visualisation
- classification models
- hierarchical clustering
- decision trees
- geographic mapping
- Microsoft Word for the original analytical report

Orange allowed the analysis to be developed through connected visual widgets rather than conventional programming scripts.

---

# Data

The project uses several datasets.

## `Census_Data.csv`

The main census dataset contains approximately **1.66 million records**.

Variables include:

- age;
- class of worker;
- education;
- marital status;
- occupation;
- place of birth;
- hours worked per week;
- sex;
- race;
- state; and
- income.

Because the file is approximately **94 MB**, it is not stored directly in this repository.

The original file has been retained locally.

---

## `Attribute_Values.csv`

This lookup file is included in the repository and was used to interpret coded variables within the census data.

It provides descriptive labels for categorical attributes such as:

- state;
- education;
- occupation;
- marital status;
- place of birth; and
- other coded census variables.

---

## `voting_2020.csv`

This dataset contains state-level results from the **2020 US Presidential election**.

Fields include:

- state;
- candidate;
- political party;
- candidate votes;
- total votes; and
- simplified party classification.

The voting data was combined with aggregated census information to investigate relationships between state demographics and election outcomes.

---

## Geographic Coordinate Data

A separate dataset containing **latitude and longitude coordinates for US states** was also used.

This was joined to the census and election datasets through the state field so that geographic visualisations could be produced in Orange.

The original coordinate file is not currently included in this repository.

---

# Part 1: Data Preprocessing

Because the original census dataset was very large, a **random sample of 5,000 observations** was selected in Orange to make the exploratory workflow computationally manageable.

Several preprocessing operations were then performed.

These included:

- restructuring variables using the **Edit Domain** widget;
- using `Attribute_Values.csv` to interpret coded attributes;
- duplicating selected variables where both numeric and descriptive versions were required;
- checking the resulting dataset using the Data Table widget;
- identifying outliers;
- separating inliers and outliers;
- reviewing feature statistics;
- examining distributions;
- producing scatterplots; and
- producing box plots.

The analysis focused primarily on the inlier observations after the initial outlier assessment.

---

# Part 2: Fairness in Income Distribution

The second section investigates whether income differs across demographic groups.

## Income Distribution

The original income variable showed a strongly skewed distribution, with most observations concentrated at lower income levels and a smaller number of very high-income observations.

A logarithmic transformation was therefore explored to reduce the influence of extreme values and make underlying patterns easier to interpret.

A Zipf-style analysis was also used to examine the relationship between income and income rank.

---

## Sex and Income

Income distributions were compared between males and females using:

- box plots;
- scatterplots; and
- a Student's t-test.

The coursework found a statistically significant difference in mean income between the groups within the analysed sample.

---

## Place of Birth and Income

US-born and non-US-born observations were also compared.

Visual inspection suggested relatively small differences between the groups, and the statistical test did not identify a significant difference in mean income within the analysed sample.

---

## Race and Income

Income was also compared between race groupings using graphical analysis and statistical testing.

Differences were identified within the analysed sample, although the coursework notes the importance of considering dataset imbalance and other potentially confounding factors.

---

# Income Relationships

The project also examines relationships between income and several continuous or ordered variables.

## Age

Age showed a positive relationship with income, although the raw correlation was relatively weak.

The relationship became clearer after applying a log transformation to income.

---

## Hours Worked

Hours worked per week also showed a positive relationship with income.

As with age, log-transforming income helped make the underlying relationship more visible.

---

## Education

Education level was positively associated with income.

The project investigates this visually and through correlation analysis before exploring education further in the predictive modelling section.

---

# Part 3: Predicting Income

The third section moves from descriptive analysis to **machine learning classification**.

## Income Classification

Income was divided into two groups:

```text
Low Income
High Income
```

A threshold of approximately **$40,000**, corresponding to the median income in the analysed sample, was used to define the two classes.

Multiple classification algorithms were then evaluated in Orange.

---

## Models

The coursework compared several machine-learning classifiers.

The strongest-performing models in the analysis were:

- **Logistic Regression**
- **Naive Bayes**

Performance was assessed using Orange's **Test & Score** functionality.

Metrics considered included:

- classification accuracy;
- area under the ROC curve;
- precision;
- recall; and
- F1 score.

ROC analysis was also used to compare model discrimination.

---

# Feature Ranking

Orange's feature-ranking tools were used to investigate which variables were most informative for income prediction.

Important predictors included factors associated with:

- working hours;
- occupation;
- education; and
- employment characteristics.

Demographic variables were also examined, although the analysis indicated that work and education-related factors were generally stronger predictors of income.

---

# Part 4: Demographics of the 2020 US Election

The project then combines census information with **2020 Presidential election results**.

The census and voting datasets were aligned using the state field.

The latitude and longitude dataset was then joined so that US state maps could be created.

---

## State-Level Aggregation

Census information was aggregated to state level to investigate characteristics including:

- mean age;
- mean income; and
- mean education level.

These state-level demographic variables were then compared with election outcomes.

---

# Geographic Analysis

Geographic visualisations were created to compare demographic characteristics with state-level voting outcomes.

Maps were produced for measures including:

- age;
- income; and
- education.

These visualisations provided a geographic view of how demographic patterns varied across states.

---

## Hierarchical Clustering

**Hierarchical clustering** was used to identify natural groupings within the state-level data.

The resulting clusters were incorporated into the geographic analysis to investigate whether states with similar demographic characteristics also showed similar voting patterns.

This demonstrates the use of **unsupervised learning** alongside traditional descriptive analysis.

---

# Election Scatterplots

Scatterplots were also used to investigate relationships between state demographics and political outcomes.

The coursework explored questions including whether:

- higher-income states showed different voting patterns;
- states with higher average educational attainment were more likely to support particular parties; and
- demographic characteristics appeared to form geographic or political clusters.

The analysis emphasises that these results represent **associations rather than causal relationships** and that additional variables could influence voting behaviour.

---

# Part 5: Independent Data Mining Investigation

The final section independently investigates the hypothesis:

> **Married people are more likely to be on a higher income.**

Several analytical techniques were used to examine this question.

---

## Scatterplot Analysis

Marital status was compared with income using scatterplots.

The visualisation indicated that married individuals occupied a wider income range and included many higher-income observations.

---

## Box Plot Analysis

Box plots were used to compare income distributions between marital-status categories.

The married category showed a higher median income within the analysed sample.

---

## ANOVA

An **analysis of variance (ANOVA)** test was used to investigate whether mean income differed across marital-status groups.

The analysis identified statistically significant differences between the groups within the sample.

---

## Distribution Analysis

Income distributions were compared across marital-status categories.

The married group extended further into higher income ranges than several of the other categories.

---

# Decision Tree

A **decision tree** was used to further investigate the relationship between income and marital status.

The tree identified income thresholds associated with different marital-status distributions.

Higher-income branches contained a greater proportion of married observations.

However, the coursework correctly treats this as an **association rather than evidence that marriage causes higher income**.

Potential influences such as:

- age;
- culture;
- employment;
- education; and
- dataset imbalance

must also be considered.

---

# Analytical Workflow

A simplified representation of the project workflow is:

```text
Census Data
     ↓
Random Sampling
     ↓
Variable Preparation
     ↓
Outlier Detection
     ↓
Exploratory Data Analysis
     ↓
Demographic Income Analysis
     ↓
Classification Models
     ↓
Feature Ranking
     ↓
State-Level Aggregation
     ↓
Merge with Election Data
     ↓
Geographic Analysis
     ↓
Hierarchical Clustering
     ↓
Independent Decision-Tree Investigation
```

---

# Repository Structure

```text
us-census-voting-data-mining/
│
├── README.md
├── .gitignore
├── Data Mining Coursework.pdf
│
└── data/
    ├── README.md
    ├── Attribute_Values.csv
    └── voting_2020.csv
```

The following large/local data dependencies are intentionally not stored directly in the repository:

```text
Census_Data.csv
US state latitude/longitude dataset
```

---

# Coursework Report

The original coursework report is included as:

```text
Data Mining Coursework.pdf
```

The report contains screenshots from the Orange workflows and visual outputs used throughout the original analysis.

These include:

- scatterplots;
- box plots;
- distributions;
- feature statistics;
- statistical test outputs;
- classification results;
- ROC curves;
- feature rankings;
- geographic maps;
- clustering outputs; and
- decision trees.

---

# Skills Demonstrated

This project demonstrates experience in:

- Orange Data Mining;
- visual machine-learning workflows;
- large dataset analysis;
- data preprocessing;
- random sampling;
- outlier detection;
- exploratory data analysis;
- categorical data preparation;
- statistical testing;
- Student's t-tests;
- ANOVA;
- Pearson correlation;
- logarithmic transformation;
- classification;
- logistic regression;
- Naive Bayes;
- ROC analysis;
- feature ranking;
- hierarchical clustering;
- decision trees;
- data integration;
- geographic data analysis;
- election data analysis;
- demographic analysis;
- fairness-oriented analysis;
- interpreting confounding variables; and
- communicating analytical results visually.

---

# Key Strengths of the Project

This project covers several different areas of the data-science workflow within a single analytical study.

It demonstrates the ability to:

- work with a dataset containing more than one million observations;
- interpret coded real-world data;
- reduce computational complexity through sampling;
- identify and investigate outliers;
- evaluate demographic differences statistically;
- transform highly skewed variables;
- compare machine-learning classifiers;
- assess feature importance;
- combine information from multiple data sources;
- use unsupervised clustering;
- analyse geographic patterns; and
- distinguish correlation from causation when interpreting results.

---

# Limitations

Several limitations should be considered when interpreting the analysis.

The main modelling workflow uses a sample of the original census dataset rather than every observation.

Some demographic groups are unevenly represented within the data, which can influence comparisons.

The election analysis uses aggregated state-level information. Relationships identified at state level should therefore not be interpreted as evidence about the behaviour of individual voters.

The analysis is observational and primarily exploratory. Statistical relationships do not demonstrate causation, and variables such as age, occupation, education, geographic location and other socioeconomic factors may act as confounders.

---

# Academic Context

This repository contains work completed as part of an **MSc Data Science Data Mining module**.

The project is included in my data science portfolio to demonstrate practical experience with:

- visual data-mining workflows;
- statistical analysis;
- machine learning;
- clustering;
- geographic analysis; and
- interpretation of large real-world datasets.

---

## Author

**Gabriella Davis**

MSc Data Science

GitHub: `gabriella-davis0505`
