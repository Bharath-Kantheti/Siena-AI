# Custom Sentiment Analysis Model

This repository contains the code and resources for training and evaluating a custom sentiment analysis model. The model categorizes customer tickets into five sentiment categories: 'Strong Negative', 'Mild Negative', 'Neutral', 'Mild Positive', and 'Strong Positive'. The project includes synthetic data generation, model training, evaluation, and deployment considerations.

## Table of Contents

- [Project Structure](#project-structure)
- [Setup Instructions](#setup-instructions)
- [Data Generation](#data-generation)
- [Model Training](#model-training)
  - [Model 1: Baseline](#model-1-baseline)
  - [Model 2: Adjusted Learning Rate](#model-2-adjusted-learning-rate)
  - [Model 3: XLNet](#model-3-xlnet)
- [Model Evaluation](#model-evaluation)
- [Deployment Considerations](#deployment-considerations)
- [Authors](#authors)
- [License](#license)

## Hugging Face link - https://huggingface.co/BharathBOLT/5class_sentimentClassifier

## Project Structure

```plaintext
project-root/
│
├── data/
│   ├── train_data.csv                 # Generated training dataset
│   ├── test_data.csv                  # Generated test dataset
│   └── validation_data.csv            # Generated validation dataset
│
├── models/
│   └── model/                         # Directory for storing the trained model and tokenizer
│   └── model1/                        # Directory for storing the trained model and tokenizer
│   └── model2/                        # Directory for storing the trained model and tokenizer
│
├── notebooks/
│   ├── data_generation.ipynb          # Notebook for generating synthetic data
│   ├── model_training.ipynb           # Notebook for training the model
│   └── model_evaluation.ipynb         # Notebook for evaluating the model
│
├── src/
│   ├── generate_data.py               # Python script for generating synthetic data
│   ├── train_model.py                 # Python script for training the model
│   ├── evaluate_model.py              # Python script for evaluating the model
│   └── utils.py                       # Utility functions (e.g., for tokenization, metrics)
│
├── docs/
│   ├── deployment_considerations.md   # Document discussing deployment considerations
│   └── optimization_report.md         # Document outlining any model optimizations
│   └── how_to_setup       .md         # Document to setup
│
├── README.md                          # Instructions for installation, running, and testing
├── requirements.txt                   # List of dependencies (e.g., transformers, pandas)
├── .gitignore                         # File to ignore unnecessary files and directories in Git
└── LICENSE                            # (Optional) License for your project
