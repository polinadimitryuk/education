# Education Project 

> In this project, I looked at how different socioeconomic factors are related to average ACT scores. I used two datasets: EdGap data and school information for the 2016–2017 school year. The ACT variable also includes an ACT-equivalent score when a school reported SAT results.

> For this project, I created a few questions that I wanted to answer:

> 1. Which socioeconomic factors have the strongest relationship with average ACT scores?
> 2. Does using multiple socioeconomic factors give a better model than using median income alone?
> 3. Does adding just a state predictor improve the model?
> 4. Does adding state and charter school predictors improve the model, and is the charter predictor still important after including the other factors?

---

## Project Overview

- **Objective:** This project examines the relationship between ACT scores and socioeconomic factors.
- **Domain:** Education
- **Key Techniques:** Data Cleaning, Exploratory Data Analysis (EDA), Data Visualization, Correlation Analysis, Linear and Multiple Regression, Model Comparison, ANOVA

---

## Project Structure

```
├── data/---ccd_sch_029_1617_w_1a_11212017.csv  # Raw and processed data
     ├── EdGap_data.xlsx
     ├── ccd_sch_029_1617_w_1a_11212017.csv 
     └── education_clean.csv
           
├── code/
        └── Education.ipynb  # Jupyter notebooks and Python scripts
├── reports/
        └── report        # Generated reports and visualizations
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

To run the analysis, open folder 'code'->Education.ipynb and run the cells in given order. 
The notebook currently uses file paths from my computer, so the paths for the two input datasets and path where 'education_clean.csv' saved need to be updated.

---

## Results

The results show that socioeconomic predictors are related to average ACT scores in schools from the dataset. Free or reduced-price lunch has the largest absolute standardized coefficient in the reduced model. Using several socioeconomic factors gives a much better fit than using median income alone. The reduced model also gives almost the same results as the full socioeconomic model.

Adding the state predictor increases R-squared from 0.6276 to 0.6776 and reduces Mean Absolute Error from 1.1523 to 1.0369 ACT points. Adding the charter predictor after state increases R-squared only slightly, to 0.6777, while adjusted R-squared and Mean Absolute Error stay almost the same. The charter predictor is not statistically significant after including the other factors (p = 0.401).

I would choose the socioeconomic plus state model as my final model. It gives almost the same results as the model with both state and charter, but uses fewer predictors.

There are limitations. The data cover only 19 states (it was 20 before I cleaned data), some predictor values were imputed, and there are still some large prediction errors. 
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