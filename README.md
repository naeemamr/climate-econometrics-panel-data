# Climate Impact on Economic Indicators

This repository presents an **applied econometric analysis** of the impact of climate conditions and climate-related policy participation on macroeconomic performance. The analysis focuses on estimating the effect of **NGFS membership** on **GDP growth** using **panel data methods**, with particular attention to the post–Paris Agreement period.

## Project Context
This project was developed as part of the **MSc in Business Informatics** at the German International University, within the *Advanced Data Analysis* course. The project emphasizes **causal inference, model specification, and statistical validity** in a climate–economy setting.

## Data
- Balanced panel dataset covering **103 countries** over **1990–2023** (N = 3,502)
- Macroeconomic outcome:
  - GDP growth
- Climate variables:
  - Temperature
  - Rainfall
  - Heating Degree Days (HDD)
  - Cooling Degree Days (CDD)
- Demographic variable:
  - Population
- Policy indicator:
  - NGFS membership
- Country classification:
  - Developed vs developing economies

## Empirical Strategy
The primary identification strategy relies on **difference-in-differences (DiD)** with **two-way fixed effects**, exploiting variation across countries and over time. The baseline model compares GDP growth in NGFS and non-NGFS countries before and after the Paris Agreement (2015), controlling for country-specific heterogeneity and global shocks.

An **event-study specification** is used to:
- Examine dynamic treatment effects
- Assess the validity of the parallel trends assumption

To capture heterogeneity, the treatment effect is interacted with a development indicator, allowing responses to differ between developed and developing economies.

## Control Variable Selection
Control variables are chosen to mitigate **omitted variable bias** by accounting for climate and demographic factors that affect GDP growth and may be correlated with NGFS participation or the post-Paris period. Selection is informed by economic theory, climate science, and exploratory data analysis.

### Rainfall
Rainfall is a key climate variable influencing agricultural output, infrastructure stability, and disaster risk. Although its contemporaneous correlation with GDP growth is weak, statistical tests indicate significant effects on inflation during extreme rainfall events. Rainfall is therefore included to control for indirect and potentially lagged macroeconomic effects. The variable is normalized to ensure comparability and reduce scale-driven influence.

### Temperature, HDD, and CDD
Temperature-related measures capture climate stress affecting energy demand, labor productivity, and agricultural outcomes. Heating Degree Days (HDD) and Cooling Degree Days (CDD) quantify deviations from temperature comfort thresholds and are strongly correlated with mean temperature. Exploratory analysis shows statistically significant GDP growth differences during extreme HDD and CDD episodes.

- HDD is log-transformed to address right skewness and improve interpretability.
- Temperature and CDD are mean-centered to preserve economically meaningful deviations and capture climate anomalies rather than absolute levels.

### Population
Population size is a fundamental scaling variable for economic activity and climate exposure. Exploratory analysis reveals strong correlations between population and energy-related climate measures, indicating that aggregate climate impacts are partly driven by country size. Log-transforming population mitigates skewness and allows the model to capture proportional effects, ensuring GDP growth estimates are not confounded by scale differences.

## Model Specifications
- Two-way fixed-effects difference-in-differences model
- Event-study model for dynamic effects and parallel trends assessment
- Heterogeneous treatment effects by level of development
- Standard errors clustered at the country level

## Tools
- Python
- Pandas, NumPy
- Statsmodels
- Matplotlib
- Scikit-learn (PCA)

## Repository Structure
- `notebook.ipynb`: Main data preparation, analysis, and econometric modeling workflow
- `data/`: Data sources or documentation
- `report/`: Project report (if included)

## Author
Naeem Amr  
MSc Business Informatics (Data Science & Econometrics)
