# Optimization Report

This document outlines the optimization steps taken during the development of the sentiment analysis model. The goal was to improve model performance and efficiency through various modifications, including hyperparameter tuning and experimenting with different model architectures.

## Table of Contents

- [Objective](#objective)
- [Optimization Steps](#optimization-steps)
  - [Step 1: Baseline Model](#step-1-baseline-model)
  - [Step 2: Adjusted Learning Rate](#step-2-adjusted-learning-rate)
  - [Step 3: Experimenting with XLNet](#step-3-experimenting-with-xlnet)
- [Results](#results)
- [Conclusion](#conclusion)

## Objective

The primary objective of this optimization effort was to enhance the performance of the sentiment analysis model, particularly in terms of precision and recall, while maintaining or improving computational efficiency.

## Optimization Steps

### Step 1: Baseline Model

**Model**: `bert-base-uncased`  
**Learning Rate**: `2e-5`  
**Training Directory**: `bert_base_train_dir`

- **Rationale**: The baseline model was trained using the widely-used `bert-base-uncased` architecture. The learning rate of `2e-5` was chosen based on common practices for fine-tuning BERT models on NLP tasks.
- **Results**: The baseline model achieved reasonable performance metrics, serving as a foundation for further optimization.

### Step 2: Adjusted Learning Rate

**Model**: `bert-base-uncased`  
**Learning Rate**: `1e-5`  
**Training Directory**: `bert_base_train_dir`

- **Change Made**: The learning rate was reduced from `2e-5` to `1e-5`.
- **Rationale**: A lower learning rate allows the model to learn more gradually, which can lead to improved fine-tuning, especially for complex tasks like sentiment analysis.
- **Results**: After training with the adjusted learning rate, the model showed improved precision and recall, particularly in minority classes, indicating better generalization.

### Step 3: Experimenting with XLNet

**Model Checkpoint**: Changed from `bert-base-uncased` to `xlnet-base-cased`  
**Training Directory**: Updated to `xlnet_base_train_dir`

- **Change Made**: The model architecture was switched from BERT to XLNet, a model known for its autoregressive capabilities, which can capture longer-range dependencies in text.
- **Rationale**: XLNet is designed to handle the permutation of words, potentially offering better performance on tasks where the order and context of words significantly impact sentiment.
- **Results**: The switch to XLNet resulted in a noticeable improvement in the model's ability to accurately classify tickets, particularly for nuanced sentiment categories like `Mild Negative` and `Mild Positive`. However, this improvement came with an increase in training time and computational resource usage.

## Results

| Model                  | Learning Rate | Macro Precision | Macro Recall |
|------------------------|---------------|-----------------|--------------|
| Baseline (BERT)        | `2e-5`        | 0.82            | 0.81         |
| Adjusted Learning Rate | `1e-5`        | 0.84            | 0.83         |
| XLNet                  | `1e-5`        | 0.87            | 0.86         | 

- **Precision and Recall**: The XLNet model showed the best performance in terms of both macro precision and recall, indicating a more balanced model across all classes.
- **Training Time**: The switch to XLNet increased training time significantly, which is an important consideration depending on the computational resources available.

## Conclusion

The optimization steps, particularly the switch to XLNet, significantly improved the model's ability to classify sentiments accurately across different categories. However, this improvement came at the cost of increased training time and resource usage. Depending on the use case and available resources, the choice between the optimized models (BERT with adjusted learning rate or XLNet) should be made carefully.

Future optimization efforts could focus on:
- Further hyperparameter tuning for XLNet.
- Exploring other model architectures like RoBERTa or GPT-based models.
- Implementing advanced techniques like knowledge distillation to reduce model size while maintaining performance.

