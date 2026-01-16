# E-commerce-Conversion-Rate-Optimization-A-B-Test-Analysis

## Business Problem
An e-commerce company redesigned its product page to improve user experience and increase purchases. The goal of this experiment is to evaluate whether the new design (Variant B) improves conversion and revenue compared to the existing design (Control A).

## Hypothesis
H₀: The new product page does not change the session-level conversion rate.  
H₁: The new product page increases the session-level conversion rate.

## Experiment Design
Unit of Randomization -	User  
Unit of Analysis - Session  
Control (A) -	Original product page  
Variant (B)	- Redesigned product page  
Assignment - Deterministic user-level hashing (50/50 split)  
Dataset Size - 74,817 clickstream events

## Metrics
Primary Metric - Session Conversion Rate (% of sessions with ≥1 purchase)  
Secondary Metrics - Add-to-cart rate, Revenue per session, Funnel progression  
Guardrail Metrics - Bounce rate, Session duration

## Data Preparation
Parsed clickstream events into session-level observations  
Constructed funnel flags per session  
Aggregated revenue at the session level  
Assigned users deterministically to A/B groups to avoid cross-session contamination  

## Sanity Checks
Sample Ratio Mismatch (SRM) test confirmed ~50/50 traffic split  
Baseline metrics (bounce rate, session duration) were balanced across variants  

## Statistical Methods
Two-proportion z-test for conversion rate
Bootstrap resampling for revenue per session
Wilson confidence intervals for proportions

## Interpretation
The observed difference in conversion rate was not statistically significant  
Revenue per session did not show a reliable lift  
Variant B does not provide enough evidence to justify a full rollout  

## Recommendation
Do not ship the new product page in its current form  
Iterate on page design (CTA placement, pricing visibility, personalization)  
Run follow-up experiments focusing on high-intent user segments  

## Limitations
A/B assignment is simulated on historical data  
No explicit exposure logging for page variants  
User behavior may be influenced by seasonality or unobserved confounders  

## Next Experiments
CTA copy and color testing  
Personalized product recommendations  
Pricing and promotion experiments  

## Tools & Technologies  
Python (pandas, NumPy, scipy, statsmodels)  
Jupyter Notebook  
Matplotlib / Seaborn  
GitHub for version control  



