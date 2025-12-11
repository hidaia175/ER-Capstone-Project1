# 📌 Emergency Room Analytics Project

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

### Additional Business Requirement

- Provide a binary machine learning model that predicts whether a patient is likely to be admitted or discharged (1 vs 0), based on features available at arrival.  
  This supports planning for bed availability, triage prioritization, and operational readiness in the Emergency Room.

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

## 🖥 Dashboard Design


Power BI was used to convert analytical findings into *interactive visual insights*.  
The dashboard allows decision-makers to:

- Understand waiting trends *quickly and visually*
- Compare differences across patient groups
- Support discussions and hospital planning using *data-driven evidence*

Power BI was chosen because it provides:

✔ Easy visual storytelling  
✔ Clear interpretation for non-technical audiences  
✔ Professional presentation suitable for academic and hospital settings

---

## 📌 Dashboard Progress

### ✔ Page 1 — Overview (Completed)

This page currently contains:

- *Pie Chart – Waiting Time by Patient Gender*  
  Shows waiting time distribution across male, female, and non-classified patients.

- *Line Chart – Waiting Time Trend by Age*  
  Displays how average waiting time varies across different age ranges.

- *Formatted title and layout styling*

This page provides a simple high-level view of how waiting differs across genders and age trends.
![page 1](https://github.com/user-attachments/assets/6a2653e3-5ad4-4ade-b6d9-45e4536509bb)

### 🔹 Page 2 — Patient Demographics

This page mirrors the analysis done in the Jupyter notebook and includes:

- *Patient Age Distribution* — shows how ages are spread across patients.
- *Gender Distribution Pie Chart* — visualizes male, female, and unclassified proportions.
- *Referral Source Breakdown* — shows where patients were referred from.

![page 2](https://github.com/user-attachments/assets/6dfa9487-8b4e-4385-a3f2-d8cccee80933)
These visuals help understand who visits the ER most frequently and from which sources.
### Hypothesis 1 Visualization  
This image represents the visual output for Hypothesis 1 in Power BI.
![Hypothises 1](https://github.com/user-attachments/assets/895a2cf9-dcd8-416e-935e-d89b0e6fcf56)

### Hypothesis 2 Visualization  
This image represents the visual output for Hypothesis 2 in Power BI.

![Hypothises 2](https://github.com/user-attachments/assets/624a40f9-cdc7-488c-bf3d-84f68b2a0682)
### 🔹 Hypothesis 3 — Seasonality Analysis

To analyze whether ER demand varies across months, a new *Month column* was created in Power BI.

📌 *What was done?*
- The original admission date field was transformed using Extract → Month in the Power Query editor.
- This generated a numerical Month attribute (1–12) representing the month of patient admission.

📌 *Why was this needed?*
- Adding this field allowed grouping patient counts by month.
- It enabled visualizing seasonal trends and confirming whether mid-year months experienced higher ER demand.

➡ This new field was then used as the X-axis in a line chart to show monthly demand variation.
![add month column](https://github.com/user-attachments/assets/8588d457-93df-41cf-9763-55090b038823)
![Hypothesis 3](https://github.com/user-attachments/assets/fab50008-18b4-4ed6-b8cc-fa2532d4770a)
### Hypothesis 4 Visualization  
This chart compares waiting time for admitted vs discharged patients.

![Hypothesis 4](https://github.com/user-attachments/assets/db9f9f2d-41c7-4bfb-8bc3-5ecd1d1675fd)


## 🐞 Unfixed Bugs

While building the dashboard in Power BI, I faced an issue related to adding a new visual (Plot visual) from the marketplace through *Get more visuals*.  
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
rmse = mean_squared_error(y_test, y_pred, squared=False)


- ### 🔹 Strategies Used to Overcome Them
To ensure compatibility with all scikit-learn versions, I replaced the above code with a manual RMSE calculation:
mse = mean_squared_error(y_test, y_pred)
rmse = np.sqrt(mse)
##  What I Learned

- Different library versions may support different parameters.  
- Reading the exact error message helps identify the root cause.  
- Understanding that RMSE = sqrt(MSE) allowed me to implement a manual fix.  
- Debugging is a normal and important part of the machine learning workflow.
- ## Deployment

The project’s interactive dashboard was deployed using *Power BI Service*.

You can access the live Power BI report through the following link:

🔗 **[ER Waiting Time Dashboard](https://app.powerbi.com/groups/me/reports/f5137f9e-f640-47c1-9e17-209d69b634de/f9ede44134280a65ce97?experience=power-bi)**

The dashboard is published to the user workspace and includes all report pages, visuals, and insights created as part of the project.


### Dataset Limitations

1. _High Missingness in Referral Source_

   The Department Referral field contained 5,400 missing records.  
   These were imputed with "Unknown" to preserve dataset size, but this reduces the ability  
   to confidently compare waiting times across referral pathways.

2. _Incomplete Satisfaction Data_

   The Patient Satisfaction Score variable had 6,699 missing values.  
   Although imputed, the absence of true responses weakens any conclusions about  
   patient experience or satisfaction-related insights.

3. _Age Distribution Bias_

   No patients below one year of age appeared in the dataset, suggesting  
   a potential sampling gap. This reduces applicability of findings to paediatric populations  
   or emergency use cases involving infants.

4. _Lack of Triage Severity or Clinical Priority Indicator_

   The dataset does not include information about patient acuity or triage level,  
   which is a critical driver of queuing and treatment priority.  
   This omission prevents deeper causal analysis into whether waiting time differences  
   are driven by medical urgency rather than demographic or timing effects.

5. _Imbalanced Referral Patterns and Limited Satisfaction Signal_

   The dominance of walk-in / unknown referral cases combined with weak satisfaction data  
   limits the strength of comparisons between referral-based and outcome-based groups.  
   While imputations preserved volume, they may distort relationships between referral behaviour,  
   perceived quality, and actual waiting experience.

6. _Unknown Imputation Impact_

   Imputation strategies (e.g., filling "Unknown" values) retained dataset completeness  
   but may reduce model accuracy or mask naturally occurring patterns—especially when comparing  
   waiting time behaviour or satisfaction trends among different patient pathways.

## 📌 Ethical Considerations

- All personal patient identifiers removed.
- Results communicated cautiously to avoid clinical bias.
- Dataset handled only for analytical—not diagnostic—purposes

## 4. Modelling & Prediction

### Objective

The goal of this section was to build a simple baseline regression model that
predicts *patient waiting time (in minutes)* using a few key features:

- Patient Age  
- Patient Gender  
- Department Referral  
- Patient Admission Flag (admitted vs discharged)

This model is *exploratory* and is used mainly to understand how well we can
predict waiting time from the available data.

### Modelling Approach

I used a RandomForestRegressor inside a scikit-learn Pipeline:

- *Preprocessing*
  - Numerical features (Patient Age, Patient Waittime when used as input in
    earlier experiments) were scaled using StandardScaler.
  - Categorical features (Patient Gender, Department Referral,
    Patient Admission Flag) were one-hot encoded using OneHotEncoder.
- *Model*
  - RandomForestRegressor(n_estimators=200, random_state=42)

The data was split into *80% training* and *20% test* using
train_test_split with a fixed random_state for reproducibility.

### Evaluation Metrics

The model was evaluated on the test set using common regression metrics:

- *Mean Absolute Error (MAE): ~13.47 minutes*  
- *Root Mean Squared Error (RMSE): ~15.96 minutes*  
- *R² Score: -0.188*

*Interpretation:*

- MAE and RMSE indicate that, on average, the model is off by about 13–16 minutes
  when predicting ER waiting time.
- The *negative R² score* means that this baseline model performs worse than a
  very simple baseline that just predicts the *mean waiting time for all patients*.
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





