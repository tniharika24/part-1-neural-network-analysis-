# Part 1: Neural Network Fundamentals and Training Behavior Analysis

## Project Overview
In this project, I built a simple feed-forward neural network to predict whether a customer is likely to churn.

The main goal of this part was not only to train a model, but also to understand how a neural network learns through:
- forward pass
- loss calculation
- backpropagation
- parameter updates

The dataset used in this project is a structured customer churn dataset.

---

## Dataset Summary
- *Rows:* 2000
- *Columns:* 17
- *Target column:* churn
- *Problem type:* Binary classification

### Input Features
The dataset contains both categorical and numerical features such as:
- region
- plan_type
- contract_type
- payment_method
- tenure_months
- monthly_charges_inr
- avg_login_days_per_month
- support_tickets_last_90_days
- payment_delay_days
- data_usage_gb
- satisfaction_score
- last_complaint_days_ago
- discount_percent
- autopay_enabled
- referral_count

customer_id was treated as an identifier and removed before model training.

---

## Tasks Covered
This notebook includes:

1. Dataset understanding
2. Data preprocessing
3. Neural network model building
4. Training and evaluation
5. Hyperparameter experimentation
6. Final reflection

---

## Data Preprocessing
The following preprocessing steps were performed:
- checked for missing values
- dropped the identifier column (customer_id)
- one-hot encoded categorical columns
- scaled numeric values
- split the data into training and testing sets
- used class weights because the target classes were imbalanced

---

## Neural Network Model
A feed-forward neural network was built using TensorFlow/Keras.

### Model structure
- input layer
- hidden layers with ReLU activation
- output layer with sigmoid activation

### Training setup
- *loss function:* binary crossentropy
- *optimizer:* Adam
- *evaluation metrics:* accuracy, ROC-AUC, confusion matrix, classification report

---

## Hyperparameter Experiments
Multiple experiments were performed by changing:
- number of hidden layers
- number of neurons
- learning rate
- batch size
- activation function

The results were compared using training accuracy, testing accuracy, and AUC.

---

## Key Learnings
- Weights and biases are the learnable parameters of the model
- Activation functions are needed to learn non-linear relationships
- Learning rate strongly affects model convergence
- Accuracy alone is not enough when the dataset is imbalanced
- ROC-AUC and confusion matrix give a better picture of classification performance

---

## Repository Structure
```bash
part-1-neural-network-analysis/
│
├── README.md
├── notebook.ipynb
├── requirements.txt
├── customer_churn_nn.csv
└── results/
    ├── target_distribution.png
    ├── evaluation_outputs.png
    ├── confusion_matrix.png
    ├── model_comparison_chart.png
    └── model_comparison_table.csv
