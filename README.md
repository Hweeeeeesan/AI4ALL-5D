# AI4ALL-5D
## Adversarial Spam Detection Project
This project investigates how spam classifiers can be improved through adversarial training. The system is designed to simulate a real-world scenario where spam evolves to bypass detection models. By building both a spam classifier and a spam generator, we aim to strengthen the robustness of spam detection methods.

## Project Overview
We developed two main components:

## Spam Classifier (Defender)
This component uses both traditional machine learning models and modern transformer-based models to detect whether a message is spam or not. Traditional models include logistic regression and XGBoost, while transformer-based models include pre-trained architectures like BERT.

## Spam Generator (Adversary)
This component fine-tunes a large language model to generate spam messages designed to evade the current spam classifier. It uses feedback from the classifier to learn and improve its outputs over time.

## Adversarial Training Process
  1. Train a baseline classifier using existing spam datasets
  2. Fine-tune a language model to generate spam messages that avoid detection
  3. Add the generated messages to the training set
  4. Retrain the classifier with the new data
  5. Repeat the process to improve both the classifier and the generator

## Datasets Used
SMS Spam Collection (UCI Machine Learning Repository)
This dataset contains 5,574 SMS messages labeled as spam or ham. It includes messages from sources like Grumbletext, the NUS SMS Corpus, and Caroline Tagg’s PhD thesis.

Enron Email Dataset
This dataset includes approximately 500,000 real emails from around 150 Enron employees, mostly in management roles. It is commonly used for research in spam detection and email classification.

Generated Data
We also create synthetic spam messages using a fine-tuned language model trained to avoid the current spam classifier.

Methods and Tools
We use the scikit-learn library for traditional models like logistic regression and XGBoost. For transformer models and language model fine-tuning, we use Hugging Face Transformers and PyTorch. Fine-tuning is done using feedback from the classifier as a reward signal. We run training and testing in environments like Google Colab and Modal, where free GPU resources such as T4s are available.
