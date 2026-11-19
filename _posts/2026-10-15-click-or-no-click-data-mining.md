---
title: "Click or No Click: Using Data Mining & Ensembling to Reach a 0.83146 Kaggle Score"
date: 2026-10-15
categories:
  - Data Mining
tags:
  - Kaggle
  - Python
  - CatBoost
  - Ensembling
---

## The Problem
Predicting whether a user will click an online ad (`click` vs. `no click`) is a classic binary classification problem in data mining, complicated by imbalanced outcomes and high-cardinality categorical features. The goal of this Kaggle competition was to apply end-to-end data mining techniques to maximize predictive ranking accuracy on unseen test impressions.

## Key Results
* Achieved a **0.83146 leaderboard score** by building a rank-averaged ensemble across multiple model families.
* Outperformed every individual standalone model we tested, with **CatBoost** providing the strongest boost when blended with linear and histogram-based tree models.

## Data
Course Kaggle competition click-through rate (CTR) dataset containing impression-level numerical and categorical features with a binary click target (public/competition benchmark data only).

## Approach
1. **Preprocessing & Validation:** Collaborated with teammates Brock Lopez and Sohyun in Python (Google Colab) to handle missing values, encode categorical variables, and maintain strict train/validation splits to prevent data leakage.
2. **Model Benchmarking:** Applied core data mining classifiers across distinct families—**Logistic Regression**, **HistGradientBoosting**, **CatBoost**, and **Neural Networks**—to compare how linear, tree-based, and neural architectures captured feature interactions.
3. **Ensemble Blending:** Implemented a Python rank-averaging script to combine out-of-fold predictions from our strongest complementary models rather than relying on a single classifier.

Linear models provided stable baseline rankings, while gradient-boosted trees (especially CatBoost and HistGradientBoosting) captured non-linear interactions across high-cardinality features. Rank-averaging their predictions reduced variance and consistently beat tuning any single model in isolation.

## What I Learned
In applied data mining, disciplined validation and model diversity matter more than chasing marginal gains from a single algorithm. Keeping reproducible pipelines and clear experiment tracking also made team ensembling much faster.