# Music Genre Classification

This project aims to predict the genre of music tracks based on audio features and metadata using various machine learning models. The task is to classify songs into multiple genres, utilizing different data preprocessing techniques and machine learning algorithms for multi-class classification.

## Table of Contents

- [Introduction](#introduction)
- [Preprocessing Approaches](#preprocessing-approaches)
- [Models Used](#models-used)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Future Work](#future-work)
- [License](#license)

## Introduction

This project is designed to classify music tracks into different genres based on a variety of audio features. Two distinct preprocessing methods were applied to handle cases where tracks are labeled with multiple genres. The primary goal is to compare the performance of several machine learning models when applied to these different preprocessing strategies.

## Preprocessing Approaches

We applied two different strategies to handle the `genre` column, which contained multiple genres for some tracks:

1. **First Approach**: Split the `genre` column into multiple rows for each genre, ensuring that each row had only one genre per track.
   - Used **TF-IDF vectorization** for text data (`artist_song`) and **scaling** of numeric features.
   
2. **Second Approach**: Selected only **one genre** per track, prioritizing genres other than `pop` where possible.
   - Simplified the dataset by reducing redundant genres, improving the balance of genres for classification.

Both approaches allowed us to evaluate how the dataset’s complexity and genre representation impacted model performance.

## Models Used

The following models were applied to the dataset and evaluated based on accuracy and F1-score:
1. **Random Forest**
2. **Neural Network**
3. **XGBoost**

## Installation

To run this project locally, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/music-genre-classification.git
2. Navigate to the project directory:
    ```bash
    cd music-genre-classification
3. Install the necessary dependencies:
    ```bash
    pip install -r requirements.txt
Note: This project was developed and tested in Google Colab to minimize dependency issues. You can run the notebook locally if you have the same versions of the required libraries installed.

## Results

The best model based on accuracy and F1-score was the **Neural Network**, which achieved:

- **Accuracy**: 0.73
- **F1-Score**: 0.72
- **ROC-AUC values for key genres**:
  - Dance/Electronic: 0.90
  - Hip Hop: 0.95
  - Pop: 0.91

### Preprocessing Comparison:

#### First Approach (Multiple Genres per Track):
- **Best Model**: XGBoost
- **Accuracy**: 0.66
- **F1-Score**: 0.64

#### Second Approach (One Genre per Track):
- **Best Model**: Neural Network
- **Accuracy**: 0.73
- **F1-Score**: 0.72

## Future Work

1. **Model Improvement**:
    - Applying ensemble methods or techniques like **Stacking** could combine the strengths of both the XGBoost and Neural Network models to further enhance performance.

2. **Handling Class Imbalance**:
    - While **SMOTE** was not suitable for this dataset due to its characteristics, experimenting with other balancing techniques or further adjusting class weights could help improve predictions for minority genres.

3. **Feature Engineering**:
    - Incorporating additional audio features, such as tempo patterns or spectral features, may help models better distinguish between similar genres.

4. **Hyperparameter Tuning**:
    - Using **Grid Search** or **Random Search** to optimize hyperparameters for both Neural Networks and XGBoost could further improve model performance.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.