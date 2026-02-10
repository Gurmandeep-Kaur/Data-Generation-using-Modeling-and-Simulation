# Data Generation using Modelling and Simulation

This repository demonstrates simulation-based dataset generation using the Cantera chemical kinetics library and comparison of multiple machine learning models for predicting the final reactor temperature of a methane-air combustion system. A synthetic dataset is generated through chemical reactor simulations and then used to train and evaluate different regression models.

---

## Overview

In this project, Cantera is used to simulate a constant-pressure methane–air combustion reactor. By varying initial temperature, pressure, and equivalence ratio, multiple simulation runs are performed to generate a dataset. Each simulation produces a final reactor temperature, which becomes the target variable.

The generated dataset is then treated as a regression problem. Several machine learning models are trained to predict the final temperature based on the input parameters. These models are evaluated using standard metrics such as Mean Squared Error (MSE) and R² score to identify the best-performing model.

---

## Simulator

Cantera is used as the chemical kinetics simulation tool. A constant-pressure batch reactor is modeled with a methane–air mixture. For each simulation run, the reactor is initialized with randomly chosen input parameters and allowed to evolve for a fixed time. The final reactor temperature is recorded as the output. This approach allows generation of synthetic combustion data without relying on real-world datasets.

---

## Parameters

Three input parameters are varied for each simulation:

- Initial Temperature (K): sampled between 900 K and 1500 K
- Pressure (atm): sampled between 1 atm and 10 atm
- Equivalence Ratio (): sampled between 0.5 and 1.5

The output parameter is:

- Final Reactor Temperature (K)

---

## Dataset Generation

A total of 1000 simulations are performed using randomly generated parameter
values within the defined bounds. For each run, Cantera computes the final reactor temperature. The input parameters and corresponding output are stored in a CSV file named `cantera_simulation_data.csv`.

The dataset contains the following columns: T_init, Pressure, Phi, and T_final. This dataset is then used for training and testing machine learning models.

---

## ML Models

The problem is treated as a regression task where the goal is to predict the final reactor temperature.

The following models are trained and evaluated:
- Linear Regression
- Random Forest Regressor
- Gradient Boosting Regressor
- Support Vector Regressor (SVR)
- K-Nearest Neighbors Regressor

The dataset is split into training and testing sets using an 80-20 split. Model performance is evaluated using Mean Squared Error (MSE) and R2 score.

---

## Results

Among all models, Random Forest Regressor achieved the lowest MSE and highest R2 score, making it the best-performing model for this dataset.

---

## Author

Gurmandeep Kaur

---
