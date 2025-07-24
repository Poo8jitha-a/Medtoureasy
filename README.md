✋ Left-Handed People Analysis – Life Expectancy Estimation

📌 Project Overview
Some notable left-handed individuals include Barack Obama, Bill Gates, Oprah Winfrey, Babe Ruth, and Marie Curie. An intriguing study from 1991 claimed that left-handed people tend to pass away roughly nine years earlier than their right-handed counterparts. Is this assertion substantiated?
This analytical project investigates whether left-handed people die earlier than right-handed people, based on historical data, age-wise death distributions, and reported handedness rates. The project uses Bayesian probability, exploratory data analysis, and visualizations to estimate age distributions at death for left- and right-handed individuals.It’s a blend of statistical modeling and hypothesis testing using real-world datasets, making it both insightful and evidence-driven.
In this data analysis notebook, we embark on a journey to unravel this fascinating phenomenon. Our objective is to employ age distribution data to ascertain whether the observed disparity in average age at death can be attributed solely to shifts in the prevalence of left-handedness over time. Leveraging the power of pandas and Bayesian statistics, we endeavor to assess the probability of attaining a specific age at death based on one's handedness, ultimately challenging the stereotype of early mortality among left-handed individuals.To put this into testing, A National Geographic survey was conducted in 1986 which 
resulted in over a million responses that included age, sex, and hand preference for throwing and writing. Researchers Avery Gilbert and Charles Wysocki analyzed this data and noticed that rates of left-handedness were around 13% for people younger than 40 but decreased with age to about 5% by the age of 80.They concluded based on analysis of a 
subgroup of people who throw left-handed but write right-handed that this age-dependence 
was primarily due to changing social acceptability . Let's explore this phenomenon using age distribution data to see if we can reproduce a difference in average age at death purely from the changing rates of left-handedness over time, refuting the claim of early death for left-handers.
📂 Dataset Information
1. Left-Handedness by Age Data (data.csv)
This dataset contains:

Age: Age in years

Male: % of left-handed males at that age

Female: % of left-handed females at that age

The dataset allows us to estimate the mean left-handedness rate over time, and compute historical prevalence by birth cohort using inferred birth years (1986 - Age).

2. Death Distribution in the US (1999) (data2.tsv)
Sourced from CDC/NCHS or National Vital Statistics Reports, this file includes:

Age: Age at death (from 0–100+)

Both Sexes: Number of deaths at that age for males and females combined

This data helps estimate the probability of dying at a certain age, which is essential to model life expectancy.

🔍 Key Analysis Steps
Data Preprocessing:

Calculated birth year (1986 - Age)

Computed Mean_lh = average of left-handed males and females

Cleaned null values in death distribution data

Visualization:

Scatter plot: % left-handed vs. age

Line plot: birth year vs. mean left-handedness

Line plot: age vs. number of deaths

Probabilistic plot: age at death vs. probability (left vs. right-handed)

Statistical Modeling:

Calculated P(left-handed | age) using historical handedness trends

Used Bayesian conditional probabilities to estimate:

P(age | left-handed)

P(age | right-handed)

Derived average age at death for each group

🤖 Key Functions Explained
P_lh_given_A(age, study_year)
Returns probability of being left-handed given a person’s age at death.

P_A_given_lh(age, death_data)
Returns probability of dying at a particular age given you’re left-handed.

P_A_given_rh(age, death_data)
Same as above, but for right-handed individuals.

P_lh(death_data)
Calculates total probability of a person being left-handed at the time of death, based on population statistics.

📈 Results & Insights
✅ Findings from 1990 Analysis:
Average age of death:

Left-handed: ~66.7 years

Right-handed: ~75.0 years

Observed gap: ~8.3 years

📊 Findings from Analysis:
Average age of death:

Left-handed: ~77.3 years

Right-handed: ~79.4 years

Improved parity: Gap reduced to ~2.1 years

📉 Conclusion: The perception that left-handed people die younger likely arises from historical bias in handedness reporting and improved societal adaptation over time.

