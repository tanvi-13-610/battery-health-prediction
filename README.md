# 🔋 battery health prediction

> predicting lithium-ion battery state of health (soh) and remaining useful life (rul) using the nasa battery dataset

![Python](https://img.shields.io/badge/Python-3.10-blue?style=flat&logo=python)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.0-orange?style=flat&logo=tensorflow)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-latest-green?style=flat)
![Gradio](https://img.shields.io/badge/Gradio-Dashboard-purple?style=flat)

---

## 📌 what it does
predicts battery state of health (soh) and remaining useful life (rul) from discharge cycle data — with a live gradio dashboard for real-time battery health monitoring.

---

## 📊 model performance

| model | rmse | r² |
|---|---|---|
| random forest | 0.0490 | 0.8324 |
| lstm | 0.0665 | 0.6910 |
| tuned rf (gridsearchcv) | 0.0441 | 0.8691 |

---

## ✨ key results
- soh predicted with ~4.4% average error (tuned rf)
- 92% classification accuracy for healthy/degrading/critical battery states
- `discharge_time` is the most important feature
- random forest outperforms lstm on this dataset

---

## 🛠 tech stack

| component | tool |
|---|---|
| models | random forest · lstm |
| tuning | gridsearchcv |
| data processing | pandas · numpy |
| visualization | matplotlib |
| dashboard | gradio |
| dataset | nasa battery dataset (kaggle) |
