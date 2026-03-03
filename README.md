# 📚 Psychometric Analysis of K–12 Library Engagement Survey

**Author:** Nandni Talreja  
**Affiliation:** UMass Amherst | Center for Education Policy  
**Supervisor:** Prof. Peter Piazza  
**Period:** September 2024 – June 2025  
**Tools:** R (psych, ggplot2, tidyverse, kableExtra) | Excel | R Markdown

---

## 🔍 Project Overview

Massachusetts education leadership needed to understand how K–12 students and teachers actually engage with school libraries — and whether those libraries were meeting their needs. Raw survey data existed across 6 schools, but it was unclean, multi-format, and inconsistent across grade levels and school types.

I was brought in as a volunteer research analyst to turn that raw data into a reproducible, psychometrically validated analysis that could inform policy and resource allocation decisions for the district.

---

## ❓ The Problem

- **1,200+ survey responses** across 6 Massachusetts schools, spread across separate Excel sheets with inconsistent formatting
- Survey questions varied by school, making cross-school comparison non-trivial
- No existing analysis pipeline — everything needed to be built from scratch
- Findings needed to be accessible to education policymakers, not just researchers

---

## 🛠️ What I Did

### 1. Data Cleaning & Preprocessing
- Loaded and standardized multi-sheet Excel data across 6 schools using `readxl` and `tidyverse`
- Converted grade columns to numeric, removed school ID columns, applied listwise deletion for missing responses
- Built a fully reproducible R Markdown pipeline so the analysis could be rerun as new data arrived

### 2. Descriptive Analysis
- Computed response frequency distributions for all Likert-scale items (1–5 scale)
- Summarized mean scores by grade and school to identify engagement patterns across age groups

### 3. Reliability & Validity Testing
- **Cronbach's Alpha** and **Guttman's Lambda-6** to assess internal consistency of survey scales
- **KMO measure** and **Bartlett's test of sphericity** to confirm data suitability for factor analysis

### 4. Exploratory Factor Analysis (EFA) & PCA
- Ran **parallel analysis** to determine the number of factors to retain per school
- Applied **EFA with varimax rotation** (ML estimation) to identify latent constructs
- Conducted **PCA** separately per school and visualized variance explained per component
- Combined schools with matching survey instruments (Mile Tree + Stony Hill; Wilbraham + MRH) for cross-school factor analysis

---

## 📊 Key Findings

- **Students overwhelmingly reported positive attitudes toward visiting the library and picking out books** (heavily skewed toward 5 on Likert scale), while research use showed more variation — suggesting libraries are seen as recreational more than academic resources
- **Parallel analysis consistently suggested a single dominant factor** across student surveys, indicating library engagement items load onto one underlying construct rather than distinct sub-dimensions
- **Teacher data** (analyzed separately) yielded a 2-factor structure via EFA, separating attitudes toward *student access to resources* from *collaboration with library staff*
- **Grade-level differences** in mean scores were modest, suggesting library attitudes are relatively stable across K–12 rather than developmentally driven

---

## 📁 Repository Structure

```
├── analysis/
│   └── library_survey_analysis.Rmd   # Full reproducible analysis pipeline
├── visuals/
│   ├── student_response_distributions.png   # Likert frequency histograms (Stony High)
│   ├── teacher_response_distributions.png   # Teacher survey response distributions
│   ├── parallel_analysis_mile_stony.png     # EFA parallel analysis scree plot (477 participants)
│   └── scree_plot_stony_hill.png            # PCA scree plot (Stony Hill)
└── README.md
```

---

## 📊 Sample Visuals

### Student Survey Response Distributions (Stony Hill School)
*Likert-scale distributions for 4 core library engagement items*

![Student Response Distributions](visuals/student_response_distributions.png)

---

### Teacher Survey Response Distributions
*Frequency and importance ratings across teacher survey items*

![Teacher Response Distributions](visuals/teacher_response_distributions.png)

---

### Parallel Analysis — Mile Tree + Stony Hill Combined (477 Participants)
*Used to determine the number of factors to retain in EFA. Actual data eigenvalues drop below simulated data after Factor 1, confirming a 1-factor solution.*

![Parallel Analysis Scree Plot](visuals/parallel_analysis_mile_stony.png)

---

### PCA Scree Plot — Stony Hill School
*First principal component explains the majority of variance, consistent with EFA findings.*

![PCA Scree Plot](visuals/scree_plot_stony_hill.png)

---

## ⚙️ How to Run

1. Clone this repository
2. Open `analysis/library_survey_analysis.Rmd` in RStudio
3. Install required packages:
```r
install.packages(c("readxl", "psych", "tidyverse", "kableExtra", 
                   "RcmdrMisc", "ggplot2", "gridExtra"))
```
4. When prompted by `file.choose()`, select your Excel data file
5. Knit to HTML for the full rendered report

> ⚠️ **Note:** Raw survey data is not included in this repository due to participant privacy agreements and IRB compliance requirements. The code will not run without supplying your own data file. The analysis pipeline and visuals are provided for portfolio and reproducibility purposes.

---

## 🔒 Privacy & Ethics

This project was conducted under IRB-compliant research protocols at UMass Amherst. All data was collected with participant consent. No personally identifiable information is included in this repository.

---

## 📬 Contact

**Nandni Talreja**  
📧 talrejanandni.da@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/nandni-talreja)  
💼 [Upwork](https://www.upwork.com/freelancers/~01883ca0f5638a8066)
