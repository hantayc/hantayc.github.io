---
title: Effects of a Four-Day Workweek on Salary Expectations
subtitle: A randomized experiment quantifying how employees trade salary for a four-day workweek
date: 2025-07-23
tags: [Causal Inference, Experimental Design, Power Analysis, Regression, R, ggplot2, Power Analysis, Linear Methods, Qualtrics]
thumbnail: /assets/images/projects/four_day_workweek_thumbnail.png
---

[📂 See the paper](/assets/files/causal_effect_salary_expectations.pdf){: .btn .btn--primary}

---

## Overview

This project evaluates the causal effect of a **four-day workweek** on employees’ **willingness to accept a salary reduction**, framing the trade-off between compensation and work–life balance in a controlled experimental setting.

While prior research on reduced workweeks has focused on productivity, job satisfaction, and well-being, this study isolates a *financial valuation* question:

> **How much salary are U.S. employees willing to forgo in exchange for a four-day workweek?**

To answer this, we implement a **between-subjects randomized experiment** and estimate the **average treatment effect (ATE)** of a four-day workweek on minimum acceptable salary.

---

## Research Design

### Experimental Setup

- **Design:** Between-subjects randomized controlled survey experiment  
- **Platform:** Qualtrics (random assignment at the respondent level)  
- **Population:** U.S. employees working traditional five-day schedules  
- **Sample Size:**  
  - Collected: 350  
  - Final analytic sample: **304** (post pilot exclusion)  
  - Treatment: 152  
  - Control: 152  

Participants were randomly assigned to one of two hypothetical scenarios:

- **Control:** Five-day workweek  
- **Treatment:** Four-day workweek  

In both conditions, respondents imagined they were unemployed and reported the **minimum salary they would accept** for the assigned work schedule.

---

## Outcome Variable

The primary outcome is the **minimum acceptable salary**, expressed as a **percentage of the respondent’s current salary**, discretized in 5% increments from **60% to 110%**.

This construction allows the estimand to be interpreted as a **salary reduction premium** associated with workweek length.

---

## Power Analysis

Prior to data collection, we conducted a **simulation-based power analysis** to determine the minimum detectable effect.

- **Target effect size:** 5 percentage points  
- **Power:** 80%  
- **Design:** Two-sample comparison (between-subjects)  
- **Required N:** ≈ 250  

The final sample of 304 observations exceeds this threshold, providing adequate power to detect economically meaningful differences while controlling Type II error.

---

## Randomization Validation

To verify that Qualtrics’ random assignment produced balanced groups, we conducted a **randomization check**:

- Null model: treatment ~ 1  
- Full model: treatment ~ demographics + employment + satisfaction covariates  
- Statistical test: F-test comparing nested models  

**Result:**  
No covariates were statistically significant predictors of treatment assignment (p > 0.05), indicating successful randomization and supporting a causal interpretation of downstream estimates.

---

## Estimation Strategy

We estimate the **Average Treatment Effect (ATE)** using a reduced-form linear regression:

$$Y_i = \alpha + \beta \cdot \text{Treatment}_i$$

Where:
- $Y_i$ = minimum acceptable salary (% of current salary)  
- $\text{Treatment}_i$ = indicator for four-day workweek  
- $\beta$ = causal effect of interest  

Under random assignment, \(\beta\) consistently estimates the ATE without additional covariate adjustment.

---

## Results

### Main Findings

- **Estimated ATE:** −2.07 percentage points  
- **Interpretation:**  
  Employees offered a four-day workweek are willing to accept, on average, a **~2 percentage point larger salary reduction** than those offered a five-day schedule.
- **Statistical significance:**  
  Marginally significant at the 10% level (p < 0.1)

While modest in magnitude, this effect is directionally consistent with prior international evidence and suggests a non-trivial valuation of reduced work time even under conservative assumptions.

---

## Visualization

The analysis includes:
- Kernel density plots comparing salary distributions across groups  
- Model-based predictions with 95% confidence intervals  
- Clear separation in distributional mass favoring greater salary flexibility in the treatment group  

---

## Key Assumptions & Limitations

- Hypothetical framing may attenuate real-world behavioral responses  
- Discrete salary bins limit outcome granularity  
- Short-term stated preferences may differ from long-run labor market behavior  

Despite these constraints, internal validity is strong due to randomization and transparent estimation.

---

## Takeaway

This study provides causal evidence that U.S. employees place **measurable economic value** on reduced workweeks, even when framed as a direct salary trade-off. The results support the idea that work schedule flexibility functions as a form of non-monetary compensation and should be considered explicitly in labor market and organizational design decisions.

---

## Methods Keywords

Causal Inference · Average Treatment Effect · Randomized Experiment · Power Analysis · Linear Regression · Survey Design · Labor Economics