# Custom Sentiment Analysis

## Setup Instructions

### Prerequisites

- Python 3.7 or higher
- Google Colab or a local environment with access to a GPU (recommended for training)
- An active Huggingface account and token

### Installation

1. **Clone the repository:**

    ```bash
    git clone https://github.com/Bharath-Kantheti/custom-sentiment-analysis.git
    cd custom-sentiment-analysis
    ```

2. **Install the required Python packages:**

    ```bash
    pip install -r requirements.txt
    ```

3. **Set up your Huggingface token:**

   - Obtain your Huggingface token from your Huggingface account.
   - Store the token securely, as it will be needed to access models and datasets.

### Data Generation

To generate the synthetic dataset, follow these steps:

1. Open `notebooks/data_generation.ipynb` in Google Colab or your local Jupyter environment.
2. Execute the cells sequentially to generate synthetic data.
3. The generated datasets (`train_data.csv`, `test_data.csv`, `validation_data.csv`) will be saved in the `data/` directory.

### Model Training

#### Model 1: Baseline

- **Model:** `bert-base-uncased`
- **Learning Rate:** `2e-5`
- **Training Directory:** `bert_base_train_dir`

To train the baseline model:

1. Open `notebooks/model_training.ipynb` in Google Colab or your local Jupyter environment.
2. Execute the cells to train the model using the default settings.

#### Model 2: Adjusted Learning Rate

- **Model:** `bert-base-uncased`
- **Learning Rate:** `1e-5`
- **Training Directory:** `bert_base_train_dir`

To train the model with an adjusted learning rate:

1. Open `notebooks/model_training.ipynb`.
2. Change the learning rate in the training arguments to `1e-5`.
3. Execute the cells to train the model.

#### Model 3: XLNet

- **Model Checkpoint:** Changed from `bert-base-uncased` to `xlnet-base-cased`
- **Training Directory:** Updated `training_dir` to `xlnet_base_train_dir`

To train the model with XLNet:

1. Open `notebooks/model_training.ipynb`.
2. Update the model checkpoint:

    ```python
    model_ckpt = "xlnet-base-cased"
    ```

3. Update the training directory:

    ```python
    training_dir = "xlnet_base_train_dir"
    ```

4. Execute the cells to train the model with XLNet.

### Model Evaluation

To evaluate the trained model:

1. Open `notebooks/model_evaluation.ipynb` in Google Colab or your local Jupyter environment.
2. Execute the cells sequentially to evaluate the model on the validation dataset.
3. The notebook will output micro and macro precision and recall scores, along with a detailed classification report.
