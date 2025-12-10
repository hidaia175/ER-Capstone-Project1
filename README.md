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

## Debugging Reflection — Naming Error in Pipeline Trigger

While implementing the pipeline trigger, I initially wrote:

```python
if name == "_main_":
    main()
```

![erorr](https://github.com/user-attachments/assets/fa1844aa-0e5a-4017-9845-190185256760)
