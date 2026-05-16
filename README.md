# Evaluating Phishing Email Detection Against Adversarial Attacks: Using Traditional, Deep Learning and Transformer Models

markdown# Evaluating Phishing Email Detection Against Adversarial Attacks: Using Traditional, Deep Learning and Transformer Models

## Overview
This project evaluates six phishing email detection models across three 
adversarial attack conditions: clean emails, character substitution 
(homoglyph attacks), and a combined adversarial attack using Unicode 
homoglyphs and invisible character injection. The six models compared 
are Naive Bayes, Logistic Regression, SVM, MLP, CNN, and DistilBERT.

## Notebooks
- **phishing_email.ipynb** — Contains Naive Bayes, Logistic Regression, 
and MLP models including adversarial training and evaluation.
- **SVM_CNN.ipynb** — Contains SVM and CNN models with adversarial 
attack generation and evaluation.
- **DistilBERT.ipynb** — Contains the DistilBERT transformer model, 
fine-tuned and evaluated on clean and manipulated emails. This notebook 
requires a GPU and was run on Google Colab with a T4 GPU.

## Datasets
Two datasets were used in this project, both available on Kaggle:
- **Nazario Phishing Dataset** — https://www.kaggle.com/datasets/naserabdullahalam/phishing-email-dataset
- **Spam/Ham Dataset** — https://www.kaggle.com/datasets/venky73/spam-mails-dataset

## How to Run

All notebooks were developed and run on **Google Colab**. To run them 
yourself follow these steps:

### Option 1 — Google Colab (Recommended)
1. Download both datasets from Kaggle
2. Upload them to your Google Drive
3. Open the notebook in Google Colab
4. Update the dataset paths in the notebook to match your 
   Google Drive folder structure. For example:
```python
NAZARIO_PATH = '/content/drive/MyDrive/YOUR_FOLDER/Nazario.csv'
SPAM_PATH    = '/content/drive/MyDrive/YOUR_FOLDER/spam_ham_dataset.csv'
```
5. Run all cells from top to bottom

### Option 2 — Local Machine
1. Download both datasets from Kaggle
2. Place them in the same folder as the notebook
3. Remove the Google Drive mount cells:
```python
from google.colab import drive
drive.mount('/content/drive')
```
4. Update the dataset paths to your local file paths. For example:
```python
NAZARIO_PATH = r'C:\Users\YourName\Downloads\Nazario.csv'
SPAM_PATH    = r'C:\Users\YourName\Downloads\spam_ham_dataset.csv'
```
5. Run all cells from top to bottom

> **Note:** DistilBERT.ipynb requires a GPU to run in a reasonable 
> amount of time. It is strongly recommended to run this notebook on 
> Google Colab with GPU enabled. To enable GPU in Colab go to 
> **Runtime → Change runtime type → T4 GPU**.

## Requirements
numpy
pandas
scikit-learn
tensorflow
transformers
torch
matplotlib
scipy

## Results Summary
| Model | Clean Acc | Char Sub Acc | Adversarial Acc |
|---|---|---|---|
| Naive Bayes | 0.9369 | 0.6417 | — |
| Logistic Regression | 0.9718 | 0.5920 | — |
| Naive Bayes (Robust) | 0.9362 | 0.9318 | 0.5423 |
| LR (Robust) | 0.9681 | 0.9770 | 0.4933 |
| MLP | 0.9740 | 0.9696 | 0.4755 |
| SVM | 0.9763 | 0.9844 | 0.4718 |
| CNN | 0.9785 | 0.9748 | 0.5237 |
| DistilBERT | 0.9926 | 0.9644 | 0.5408 |