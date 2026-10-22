# Education Project 

> The purpose of this project is to inspect the datasets and examine the relationship between ACT scores and socioeconomic characteristics such as
> the unemployment rate, median household income, and the percentage of children living in married-couple families.
> In this project, I looked at how different socioeconomic factors are related to average ACT scores. I used two datasets: EdGap data and school information for the 2016–2017 school year. The ACT variable also includes an ACT-equivalent score when a school reported SAT results.
> For this project, I created a few questions that I wanted to answer:

> Which socioeconomic factors have the strongest relationship with average ACT scores? Does using multiple socioeconomic factors give a better model than using median income alone? Does adding state and charter school status improve the model, and is charter status still important after including the other factors?
---

## Project Overview

Provide a short and concise overview of the project. Mention the problem it solves, the data used, and the key outcomes or findings.

- **Objective:** This project examines the relationship between ACT scores and socioeconomic factors.
- **Domain:** Education
- **Key Techniques:** Data Cleaning, Exploratory Data Analysis (EDA), Data Visualization, Correlation Analysis, Linear and Multiple Regression, Model Comparison, ANOVA

---

## Project Structure

```
├── data/  ccd_sch_029_1617_w_1a_11212017.csv  # Raw and processed data
           EdGap_data.xlsx
           education_clean.csv    
├── code/
          Education.ipinb  # Jupyter notebooks and Python scripts
├── reports/
            report        # Generated reports and visualizations
├── requirements.txt      # Dependencies
└── README.md             # Project documentation
```

---

## Data

- **Source:** [https://www.dropbox.com/scl/fi/fkafjk8902sq8ptxh94r2/ccd_sch_029_1617_w_1a_11212017.csv?rlkey=gucrdz5f6e38bezz2y3yalxbw&dl=0]
- [https://github.com/brian-fischer/DATA-5100/blob/main/EdGap_data.xlsx]
- **Description:** School Information 2016–2017: This dataset includes school details such as state, ZIP code, school type, school level, and charter status.
- EdGap data: This dataset includes average ACT scores and socioeconomic information for schools, such as median household income, unemployment rate, college education, and free or reduced-price lunch.
- **License:** 

---

## Analysis

The first thing I did when I started inspecting the datasets was check data types, missing values, distributions, and possible errors like negative values. Then I checked what columns there were in each dataset. I merged both datasets together using the school ID, kept high schools, and filled in missing numerical predictor values.

Then I used plots and correlations to look at the relationships with ACT scores. I fitted a linear and a quadratic model for median income and compared a full socioeconomic regression with a reduced model. Then I standardized the predictors to compare their coefficients. Finally, I added state and charter predictors and used model comparisons and ANOVA to check whether they improved the fit or not.

---

## Results

The results say that socioeconomic predictors are closely related to average ACT scores in schools from the dataset. 
Free or reduced-price lunch has the strongest relationship with scores in both the correlations and the standardized regression. 
A model with several socioeconomic variables fits much better than using median income alone. I also found that the reduced model works almost as well as the full socioeconomic model.

Adding state and charter status improves the fit again, but charter status by itself is not statistically significant once the other factors are included. The overall improvement seems to come mainly from the state differences.

There are limitations. The data cover only 20 states, some predictor values were imputed, and the model errors still have outliers. 
Also, I compared how the models fit these schools rather than testing them on a separate set of schools. 

---

## Authors

- Polina Dimitryuk - [@polinadimitryuk](https://github.com/education)

---

## License

This project is licensed under the MIT License.

---

## Acknowledgements

- Python in Jupyter Notebook.
- Libraries: pandas, NumPy, Matplotlib, Seaborn, Plotly, scikit-learn, statsmodels, and openpyxl 

