# Credit Scoring Dashboard & Technical Watch

## Overview

This project is part of my Data Scientist training and focuses on building an interactive dashboard for a credit scoring application, while also carrying out a technical watch on recent advances in interpretable machine learning.

The dashboard was designed to make model predictions easier to understand for non-technical users. It provides both a business-oriented view of the credit decision and an interpretable view of the model behavior through visual explanations and client comparisons.

In parallel, the project includes a technical watch on **ProtoViT**, a recent research paper on interpretable vision transformers, as part of a broader reflection on explainability in machine learning.

---

## Project Objectives

The main goals of this project were to:

- create an interactive dashboard for a previously developed credit scoring system,
- display the predicted credit acceptance probability in a clear and beginner-friendly way,
- show the most important client information used in the decision process,
- compare one client against the overall population through interactive charts,
- provide local interpretability using SHAP values,
- deploy the dashboard in the cloud,
- and document a technical watch on recent interpretable AI research.

---

## Business Context

A credit scoring model had already been developed and exposed through an API in a previous project.  
The next step was to build a user-facing dashboard allowing customer advisors or non-technical stakeholders to explore a client profile, understand the predicted probability, and access visual explanations supporting the model output.

The challenge was not only technical, but also communicational: the dashboard needed to remain understandable for users who are not familiar with machine learning.

---

## Main Features

1. Client selection
2. Credit decision visualization
3. Client information panel
4. Population comparison
5. Model interpretability
6. Bivariate analysis

---

## Technical Watch

As part of this project, I also carried out a technical watch on explainable AI through the paper:

**Interpretable Image Classification with Adaptive Prototype-based Vision Transformers (ProtoViT)**

This paper explores how to combine:
- the performance of Vision Transformers,
- prototype-based reasoning,
- and more faithful model interpretability.

Even though the dashboard itself is related to tabular credit scoring, this technical watch helped me deepen my understanding of modern interpretability approaches and the different ways machine learning models can be made more transparent.

This part of the project reflects a broader interest in **responsible AI**, **explainability**, and user trust in machine learning systems.

---

## Project Structure

```bash
.
├── app.py
├── requirements.txt
├── Dockerfile
├── data/
│   ├── application_test.csv
│   ├── bivariate_analysis_dataset.csv
│   ├── full_test_prediction.csv
│   └── global_shap_values.pkl
├── pages/
│   ├── predictions.py
│   ├── graphs.py
│   ├── shap_explenations.py
│   └── bivariate_graph.py
├── notebooks/
├── .github/workflows/
└── 0_dashboard.ipynb
```

---

## How It Works

The Streamlit dashboard loads local client data and sends the selected client information to an external scoring API.  
The API returns:
- the prediction,
- the explained value,
- the SHAP values,
- and the feature names.

The dashboard then combines these outputs with local visualizations to provide an interactive and more interpretable user experience.

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/jeromelegal/Projet_08_OCR_Data_Scientist.git
cd Projet_08_OCR_Data_Scientist
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the app

```bash
streamlit run app.py
```

---

## Docker

A `Dockerfile` is included to containerize the dashboard.

Build the image:

```bash
docker build -t credit-scoring-dashboard .
```

Run the container:

```bash
docker run -p 8501:8501 credit-scoring-dashboard
```

---

## Deployment

This project also includes a GitHub Actions workflow used to:
- install dependencies,
- build a Docker image,
- push it to Azure Container Registry,
- and deploy it to Azure Container Instances.

This gave me hands-on experience with a simple CI/CD pipeline for a data application.

---

## What I Learned

Through this project, I improved my skills in:

- designing a data product for non-technical users,
- building interactive dashboards with Streamlit and Bokeh,
- integrating a machine learning API into a front-end application,
- using SHAP for local and global interpretability,
- deploying a containerized application to the cloud,
- and documenting research trends in explainable AI.

---

## Limitations

This is still an early-stage project, and several improvements could be made:

- improve the visual design and accessibility of the dashboard,
- add more client filters and segmentation options,
- strengthen error handling when the API is unavailable,
- make the app fully bilingual,
- and improve reproducibility by packaging the API and dashboard together.

---

## Possible Improvements

Here are a few natural next steps for this project:

- connect the dashboard to a more robust production API,
- add model monitoring indicators,
- integrate group-level filters directly into the interface,
- add richer explanation panels for business users,
- and include automated tests for the dashboard components.

---

## Author

**Jérôme Le Gal**  
Data Science student

