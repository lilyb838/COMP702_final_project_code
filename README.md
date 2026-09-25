# COMP702_final_project_code

This project investigates whether explicitly modelling relationships between entities in horse racing can improve the prediction of race outcomes.

A heterogeneous Graph Neural Network (GNN) is compared with a Multilayer Perceptron (MLP) baseline. Both models predict the probability of a horse finishing top 3 in a race.

The project uses the same dataset, target, evaluation metrics and experimental procedure for both models, allowing the effects of explicit relational structure to be investigated.

# Dataset

The original horse racing data was obtained from the following Kaggle dataset:

https://www.kaggle.com/datasets/deltaromeo/horse-racing-results-ukireland-2015-2025

The project uses a processed dataset named `raceform.csv`. This file is not included in the repository due to its size.

`raceform.csv` must be available before running the project. The 'raceform' subset is automatically created when the dataset is downloaded

# Models

## Multilayer Perceptron (MLP)

The MLP provides a standard tabular baseline in which each runner is represented independently using its features.

## Heterogeneous Graph Neural Network (GNN)

The GNN represents the data as a heterogeneous graph containing different entity types and their relationships. The model uses message passing to update node representations before predicting the probability of a runner finishing in the top three.

# Hyperparameter tuning

The hyperparameter tuning was run, and then the model's hyperparameters updated accordingly. The hyperparameter tuning code does not need to be run in order for the main experiment to run.

# Evaluation

The models are evaluated using: ROC-AUC, AUPRC, and Log Loss.

Statistical analysis is also performed to compare model performance across matched seeded runs, however it was calculated manually, and is not contained in any code.

# Requirements

The Python packages required to run the project are listed in `requirements.txt`.

Install the required packages using
pip install -r requirements.txt

# Running the Project

1. Download the original horse racing dataset from the Kaggle link above.
2. Place the downloaded 'raceform.csv' dataset in the same folder as the project code.
3. Install the required Python packages using `requirements.txt`.
4. Run the project using the main Python script.


# Reproducibility

The project uses fixed random seeds for the reported experimental runs. The seed is fixed to 42 in the code, this was manually changed each time the models were run on a new seed (42-47)

# Additional Files

The repository also contains several additional files that are not required for the main experiment to run. They are used to provide additional analysis during the project , or to to document the manual verification of entity identities against external sources.

These files are:

- subset_evaluation.py
- verification.py
- tables_for_unique_ids.py
