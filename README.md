# 🧠 AI Powered Smart Cognitive Tracker

This repository represents the final integration point of a multimodal AI system designed to detect early signs of mental health issues in adolescents. It brings together multiple independently trained AI models and fuses select components to deliver a comprehensive cognitive and emotional risk analysis.

---

## 🔍 What This Repository Contains

This is the **main fusion repository** of the project. It includes:

- ✅ **Fusion between Vision Transformer (ViT)** and **XGBoost** models
- ✅ References to 4 **individually trained models** stored in separate GitHub repositories
- ✅ Explanation of how the fusion is performed using **output extracts** from those model repositories
- ✅ Clarification that **BERT** and **Wav2Vec** are used as **standalone predictors** outside the fusion pipeline

---

## 🔗 Linked Repositories (Individual Models)

Each of the following models is hosted in a separate GitHub repository:

| Model | Task | Repo |
|-------|------|------|
| 🧠 BERT | Text emotion detection (standalone) | [BERT Text Emotion Analyzer](https://github.com/Suroochi3/bert-text-emotion-analyzer) |
| 🎭 ViT | Facial expression recognition (used in fusion) | [ViT Facial Expression Analyzer](https://github.com/Suroochi3/vit-facial-expression-analyzer) |
| 🔊 Wav2Vec 2.0 | Voice emotion detection (standalone) | [Wav2Vec Voice Emotion Analyzer](https://github.com/Suroochi3/wav2vec-voice-emotion-analyzer) |
| 📊 XGBoost | Academic & health data analysis (used in fusion) | [XGBoost Mental Health Predictor](https://github.com/Suroochi3/xgboost-mental-health-predictor) |

---

## 🔗 Fusion Logic (ViT + XGBoost Only)

In this repository, we perform **partial multimodal fusion** between the **ViT** and **XGBoost** models:

- ✅ **ViT** provides emotion predictions from facial expressions
- ✅ **XGBoost** provides risk predictions based on academic and health records
- These predictions are then **fused** into a joint decision using simple concatenation or voting mechanisms.

The output predictions used for fusion are **not generated here**, but are instead:
> 📁 **Pre-extracted and available inside their respective repositories (ViT and XGBoost)**

---

## 🚫 Not Fused in This Repository

- ✅ **BERT** and **Wav2Vec** models are **standalone** components of the full system. They are trained independently and used separately from this fusion pipeline.
- Their individual outputs contribute to the overall system evaluation but are **not integrated into the fusion model here**.

---

## 📂 Files in This Repo

- `MULTI_MODEL_FUSION.ipynb`  
  → Main notebook that loads output predictions from ViT & XGBoost and performs fusion.

- `README.md`  
  → This file.

- `requirements.txt` *(optional)*  
  → Add if you want to auto-install libraries.

---

## 🚀 Run in Google Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Suroochi3/AI-Powered-Smart-Cognitive-tracker/blob/main/MULTI_MODEL_FUSION.ipynb)

---



## 🧠 System Architecture Summary

Text (BERT)       → Standalone
Voice (Wav2Vec)   → Standalone

Image (ViT)  ↘ 
              → Partial Fusion → Final Risk Score
Tabular (XGB) ↗

## 📦 Requirements

```bash
pip install pandas scikit-learn xgboost torch torchvision timm
