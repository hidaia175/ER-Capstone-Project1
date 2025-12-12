<h2 align="center">Emergency Room Analytics Project</h2>

![ER room](https://github.com/user-attachments/assets/0dc40883-071f-40e5-9a76-8b0abe0f153b)


## Dataset Content

The dataset used in this project was sourced from **Kaggle** and contains detailed hospital emergency room (ER) records.  
It includes demographic information, admission details, referral sources, satisfaction scores, and waiting time data.

### Dataset Size

- **Rows:** 9,216
- **Columns:** 12

This dataset is suitable for exploratory data analysis, hypothesis testing, and building prediction models related to ER wait times.

You can access the dataset on Kaggle at the following link:  
🔗 **[Hospital Emergency Room Dataset on Kaggle](https://www.kaggle.com/datasets/laxdippatel/hospital-emergency-room-dataset?utm_source=chatgpt.com&select=Hospital+ER_Data.csv)**

The file is relatively small and well below GitHub’s 100 GB repository limit.

## Project Overview

This project analyzes Emergency Room (ER) patient patterns to understand waiting time behaviors, referral impacts, seasonal demand, and admission outcomes.  
The insights support data-driven operational planning and predictive modelling.

### Extended Project Objective

In addition to analyzing ER patient behaviour and waiting time patterns, this project aims to build a predictive machine learning component that classifies patients into two outcomes — admitted (1) or not admitted (0).

The objective is to move beyond descriptive insights and provide a forward-looking capability that helps anticipate admission outcomes based on patient features such as age, arrival characteristics, and waiting behaviour.

## 📌 Business Requirements

- Identify factors affecting ER waiting time.
- Understand seasonal and time-based demand changes.
- Compare walk-in versus referred patient behaviors.
- Support hospital planning using analytical insights.


## 📌 Hypotheses & Validation Approach

### 🔹 Hypothesis 1

Older patients experience longer waiting times.  
_Validation:_ grouped age analysis + boxplots.

### 🔹 Hypothesis 2

Referral type influences waiting time.  
_Validation:_ swarm/violin plot comparing walk-ins vs referred cases.

### 🔹 Hypothesis 3

ER demand varies seasonally across the year.  
_Validation:_ monthly trend line analysis.

### 🔹 Hypothesis 4

Admitted patients wait longer than discharged patients.  
_Validation:_ violin plot comparing outcome groups

## Overall Recommendations
- Improve triage processes for older patients to reduce waiting times.
- Optimize staffing levels during peak seasonal demand.
- Review referral pathways to improve efficiency for walk-in cases.

## 📌 Project Plan

- Data collection and import
- Data cleaning and preparation
- Exploratory data analysis (EDA)
- Identifying key business questions
- Designing appropriate visualisations
- Building the Power BI dashboard
- Interpreting insights and summarising findings
- Addressing limitations and challenges
- Documenting the process
- Using generative AI for support and refinement

## Analysis Techniques Used

- Descriptive statistics to understand distributions and basic patterns.
- Grouped comparisons (age, gender, referral, admission status) to explore differences in wait times.
- Trend analysis for monthly and seasonal patterns.
- Missing value handling (imputation for referral source and satisfaction score).
- Exploratory machine learning model (RandomForestRegressor) to test whether waiting time could be predicted.
  - The model was used only for analytical insight and not deployed in the Power BI dashboard due to limited predictive performance.

### Limitations

- High missingness in key fields (referral source, satisfaction score).
- No triage severity variable limited deeper clinical analysis.
- Imputation may introduce bias.
- The model’s performance was weak (negative R²), limiting interpretability.

### Alternative Approaches

- Used imputation instead of dropping rows to maintain dataset size.
- Relied on visual analysis when statistical modeling was insufficient.
- Excluded satisfaction score from some comparisons due to high missingness.
- Treated the ML model as exploratory and not part of the BI report.

### Structure of Analysis

- Began with cleaning and validation.
- Conducted EDA to identify patterns.
- Built an exploratory ML model to test predictability.
- Created Power BI visuals to communicate insights clearly.

## 📌 Ethical Considerations

- All personal patient identifiers removed.
- Results communicated cautiously to avoid clinical bias.
- Dataset handled only for analytical—not diagnostic—purposes.

## 🖥 Dashboard Design

Power BI was used to convert analytical findings into _interactive visual insights_.  
The dashboard allows decision-makers to:

- Understand waiting trends _quickly and visually_
- Compare differences across patient groups
- Support discussions and hospital planning using _data-driven evidence_

Power BI was chosen because it provides:

✔ Easy visual storytelling  
✔ Clear interpretation for non-technical audiences  
✔ Professional presentation suitable for academic and hospital settings

---

## 📌 Dashboard Progress

### ✔ Page 1 — Overview (Completed)

This page currently contains:

- _Pie Chart – Waiting Time by Patient Gender_  
  Shows waiting time distribution across male, female, and non-classified patients.

- _Line Chart – Waiting Time Trend by Age_  
  Displays how average waiting time varies across different age ranges.

- _Formatted title and layout styling_

This page provides a simple high-level view of how waiting differs across genders and age trends.
![page 1](https://github.com/user-attachments/assets/6a2653e3-5ad4-4ade-b6d9-45e4536509bb)

### 🔹 Page 2 — Patient Demographics

This page mirrors the analysis done in the Jupyter notebook and includes:

- _Patient Age Distribution_ — shows how ages are spread across patients.
- _Gender Distribution Pie Chart_ — visualizes male, female, and unclassified proportions.
- _Referral Source Breakdown_ — shows where patients were referred from.

![page 2](https://github.com/user-attachments/assets/6dfa9487-8b4e-4385-a3f2-d8cccee80933)
These visuals help understand who visits the ER most frequently and from which sources.

### Hypothesis 1 Visualization

This image represents the visual output for Hypothesis 1 in Power BI.
![Hypothises 1](https://github.com/user-attachments/assets/895a2cf9-dcd8-416e-935e-d89b0e6fcf56)

### Hypothesis 2 Visualization

This image represents the visual output for Hypothesis 2 in Power BI.

![Hypothises 2](https://github.com/user-attachments/assets/624a40f9-cdc7-488c-bf3d-84f68b2a0682)

### 🔹 Hypothesis 3 — Seasonality Analysis

To analyze whether ER demand varies across months, a new _Month column_ was created in Power BI.

📌 _What was done?_

- The original admission date field was transformed using Extract → Month in the Power Query editor.
- This generated a numerical Month attribute (1–12) representing the month of patient admission.

📌 _Why was this needed?_

- Adding this field allowed grouping patient counts by month.
- It enabled visualizing seasonal trends and confirming whether mid-year months experienced higher ER demand.

➡ This new field was then used as the X-axis in a line chart to show monthly demand variation.
![add month column](https://github.com/user-attachments/assets/8588d457-93df-41cf-9763-55090b038823)
![Hypothesis 3](https://github.com/user-attachments/assets/fab50008-18b4-4ed6-b8cc-fa2532d4770a)

### Hypothesis 4 Visualization

This chart compares waiting time for admitted vs discharged patients.

![Hypothesis 4](https://github.com/user-attachments/assets/db9f9f2d-41c7-4bfb-8bc3-5ecd1d1675fd)

## 🐞 Unfixed Bugs

While building the dashboard in Power BI, I faced an issue related to adding a new visual (Plot visual) from the marketplace through _Get more visuals_.  
Although the installation completed successfully, the icon did not appear clearly in the visualization panel, which prevented using it in the design.

### 🔹 Why the Issue Remained Unresolved

- The location of the installed visual was not obvious in the Power BI interface.
- Manually searching inside the panel did not help in locating it.
- Time was prioritized for completing the core dashboard structure rather than deeply investigating the icon location.

### 🔹 How I Handled the Issue

- I continued using the default built-in visuals in Power BI to complete the required design.
- I plan to retry installing the visual again later or check visibility after restarting Power BI or updating plugins.
-

## Development Roadmap

### 🔹 Challenges Faced

During dashboard development, I struggled with Power BI visuals not appearing correctly on the canvas.  
Some charts were added but were too small or hidden, making it seem like nothing was working.  
Additionally, formatting elements such as text boxes and visual resizing required trial and error to align properly.

### 🔹 Strategies Used to Overcome Them

I resolved these issues by:

- Re-adding visuals and manually resizing them.
- Using formatting options to adjust visibility, borders, and alignment.
- Exploring built-in AI Q&A visuals to automate chart generation where possible.
- Iteratively testing placements and layout until the dashboard became clean and readable.

This process helped me improve troubleshooting and visual design skills.

### 🔹 Skills I Plan to Learn Next

Based on the dashboard experience, I plan to:

- Learn more advanced Power BI formatting & interactivity.
- ### 🔹 Challenges Faced
- While evaluating the regression model, I encountered an error when trying to compute the RMSE using:
  ![erorr](https://github.com/user-attachments/assets/a4c611b6-21f4-41bd-915d-d3ae709684ad)

```python
rmse = mean_squared_error(y_test, y_pred, squared=False)
```

### 🔹 Strategies Used to Overcome Them

To ensure compatibility with all scikit-learn versions, I replaced the above code with a manual RMSE calculation:

```python
mse = mean_squared_error(y_test, y_pred)
rmse = np.sqrt(mse)
```

## What I Learned

- Different library versions may support different parameters.
- Reading the exact error message helps identify the root cause.
- Understanding that RMSE = sqrt(MSE) allowed me to implement a manual fix.
- Debugging is a normal and important part of the machine learning workflow.

## Deployment

The project’s interactive dashboard was deployed using _Power BI Service_.

You can access the live Power BI report through the following link:

🔗 **[ER Waiting Time Dashboard](https://app.powerbi.com/groups/me/reports/f5137f9e-f640-47c1-9e17-209d69b634de/f9ede44134280a65ce97?experience=power-bi)**

The dashboard is published to the user workspace and includes all report pages, visuals, and insights created as part of the project.

## 4. Modelling & Prediction

### Objective

The goal of this section was to build a simple baseline regression model that
predicts _patient waiting time (in minutes)_ using a few key features:

- Patient Age
- Patient Gender
- Department Referral
- Patient Admission Flag (admitted vs discharged)

This model is _exploratory_ and is used mainly to understand how well we can
predict waiting time from the available data.

### Modelling Approach

I used a RandomForestRegressor inside a scikit-learn Pipeline:

- _Preprocessing_
  - Numerical features (Patient Age, Patient Waittime when used as input in
    earlier experiments) were scaled using StandardScaler.
  - Categorical features (Patient Gender, Department Referral,
    Patient Admission Flag) were one-hot encoded using OneHotEncoder.
- _Model_
  - RandomForestRegressor(n_estimators=200, random_state=42)

The data was split into _80% training_ and _20% test_ using
train_test_split with a fixed random_state for reproducibility.

### Evaluation Metrics

The model was evaluated on the test set using common regression metrics:

- _Mean Absolute Error (MAE): ~13.47 minutes_
- _Root Mean Squared Error (RMSE): ~15.96 minutes_
- _R² Score: -0.188_

_Interpretation:_

- MAE and RMSE indicate that, on average, the model is off by about 13–16 minutes
  when predicting ER waiting time.
- The _negative R² score_ means that this baseline model performs worse than a
  very simple baseline that just predicts the _mean waiting time for all patients_.
  This suggests that the current set of features does not explain the variability
  in waiting times very well.

Despite the weak performance, the experiment is still useful: it shows that
waiting time in this dataset is highly variable and likely influenced by other
operational factors that are not captured in the current features.

### Visualising Model Performance

To better understand the model behaviour, I plotted **Actual vs Predicted
waiting times**:

- Points close to the diagonal line (y = x) represent good predictions.
- The points are widely scattered, confirming that the model struggles to
  capture the underlying pattern in waiting times.

These plots are included in the notebook and can be referenced in the report.

![readme](https://github.com/user-attachments/assets/569d7860-e7bd-4cee-bf6d-1f8a8c3d498e)

## Main Data Analysis Libraries

- pandas
- numpy
- matplotlib.pyplot
- seaborn

## Scikit-learn Libraries

- train_test_split
- ColumnTransformer
- OneHotEncoder
- StandardScaler
- Pipeline
- RandomForestRegressor
- mean_absolute_error
- mean_squared_error
- r2_score

## Credits

### Content

- The written explanations and documentation in this project were supported by ChatGPT (OpenAI), mainly for refining text, improving clarity, and structuring sections.
- Conceptual understanding of data analysis steps was reinforced through the LMS materials provided by the training center.

### Data Source

- The dataset used in this project was obtained from Kaggle:
  https://www.kaggle.com/datasets/laxdippatel/hospital-emergency-room-dataset

### Code & Technical References

- Several code structures (e.g., preprocessing, encoding, model evaluation) were referenced from official Python library documentation:
  - Pandas documentation
  - Scikit-learn documentation
  - Matplotlib & Seaborn documentation
- Additional guidance was inspired by YouTube tutorials covering:
  - Power BI visualisation techniques
  - Python data cleaning and EDA methods

### Media

- All visuals and charts were created manually in Power BI Desktop.
- No external images or graphical media were imported into the project.

## Acknowledgements

I would like to express my appreciation to everyone who provided guidance, support, and resources throughout the development of this project. Their assistance, whether through educational materials, technical insights, or general encouragement, contributed greatly to completing this work.
