# Dataset Description

This dataset contains information on credit card transactions, used to detect fraudulent activities. Below are the key features of the dataset:

- **Time**: The number of seconds elapsed between this transaction and the first transaction in the dataset.
- **V1, V2, ..., V28**: These features are the result of a Principal Component Analysis (PCA) transformation. The original data has been processed to reduce dimensionality and enhance feature representation, thereby providing anonymized and decorrelated features.
- **Amount**: The transaction amount.
- **Class**: The target variable indicating whether the transaction is fraudulent (`1`) or not (`0`).

Note: Features `V1` to `V28` have already been processed using PCA, which ensures privacy and helps in reducing the dimensionality of the dataset.

## Compressed Dataset

Due to the large size of the dataset, it has been compressed into a zip file for easier handling and download. To use the dataset, please follow these steps:

1. Download the compressed dataset file.
2. Unzip the file in your working directory.
3. Load the dataset from the unzipped folder into your environment for analysis.

The compressed dataset contains the same information as described above, ensuring no loss of data or quality.

