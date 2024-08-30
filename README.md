# Arabic Speech - Quran Verse Recognition Using Ensemble Voting Classifier with Mistake identification - Modelling

This project implements an Arabic Speech Recognition system using an ensemble voting classifier. The model is built with Python and utilizes the Librosa library for preprocessing and feature extraction. Additionally, an Android application is included that allows users to record Quranic verses, identify the words, and check the accuracy of the recitation. The APIs for this functionality are built using Flask.

## Table of Contents

- [Project Overview](#project-overview)
- [Features Extracted](#features-extracted)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Android Application](#android-application)
- [Dataset](#dataset)
- [Model Architecture](#model-architecture)
- [Results](#results)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

Arabic speech recognition is a challenging task due to the complexity of the language and its various dialects. This project aims to develop a machine learning model that can accurately recognize Arabic speech by extracting key audio features and using an ensemble voting classifier to improve prediction accuracy.

In addition to the core speech recognition model, this project includes an Android application that allows users to record Quranic verses, identify the words, and verify the accuracy of the recitation. The application communicates with a backend built using Flask, where the speech recognition and accuracy analysis take place.

## Features Extracted

We used the following audio features for this project:

- **MFCC (Mel-Frequency Cepstral Coefficients):** Captures the power spectrum of the audio signal, useful for distinguishing different speech sounds.
- **Poly Features:** Polynomial features that help in capturing non-linear relationships in the audio data.
- **Mel Spectrogram:** Provides a visual representation of the spectrum of frequencies in a sound signal as it varies with time.
- **Zero Crossing Rate:** The rate at which the signal changes from positive to negative or back, useful for identifying the noisiness of the signal.

## Technologies Used

- **Python**: Programming language used for the entire project.
- **Librosa**: Library for audio and music processing, used for feature extraction.
- **Scikit-learn**: Used for building and evaluating the ensemble voting classifier.
- **Flask**: Web framework used to build the APIs for the Android application.
- **Android (Java/Kotlin)**: Used to develop the Android application.
- **Pandas**: For data manipulation and analysis.
- **NumPy**: For numerical operations.
- **Matplotlib**: For visualization of results.

## Installation

To run this project locally, follow these steps:

1. Clone the repository:

    ```bash
    git clone https://github.com/AlinaBaber/Arabic-Speech-Recognition-by-Machine-learning-and-feature-extraction.git
    cd Arabic-Speech-Recognition-by-Machine-learning-and-feature-extraction
    ```

2. Create a virtual environment:

    ```bash
    python3 -m venv venv
    source venv/bin/activate   # On Windows use `venv\Scripts\activate`
    ```

3. Install the required packages:

    ```bash
    pip install -r requirements.txt
    ```

## Usage

1. **Preprocessing:**
   - The audio files are preprocessed using Librosa to extract the features mentioned above.
   - The features are then normalized and prepared for training.

2. **Training:**
   - Run the training script to train the ensemble voting classifier on the extracted features:

    ```bash
    python train_model.py
    ```

3. **Testing:**
   - Evaluate the model on the test dataset:

    ```bash
    python evaluate_model.py
    ```

## Android Application

The Android application is designed to:

- **Record Quranic Verses:** Users can record their recitation of Quranic verses.
- **Identify Words:** The app processes the recorded audio and identifies the words.
- **Accuracy Check:** The app checks the accuracy of the recitation against the expected Quranic verse and provides feedback on any mistakes.

### APIs

The backend APIs are built using Flask and are responsible for:

- **Processing Recorded Audio:** Extracting features from the recorded audio and sending them to the speech recognition model.
- **Comparing Recitation:** Checking the accuracy of the recitation by comparing it with the correct text of the Quranic verse.

## Dataset

- The dataset used for this project contains Arabic speech samples, specifically focusing on Quranic verses for the Android application.
- **Note:** The dataset is not included in this repository due to size constraints. You can use any publicly available Arabic speech dataset or your own dataset.

## Model Architecture

The ensemble voting classifier combines multiple machine learning models to improve prediction accuracy. The following classifiers are used:

- **Random Forest**
- **Support Vector Machine (SVM)**
- **K-Nearest Neighbors (KNN)**

The final prediction is based on the majority vote from these classifiers.

## Results

The model achieved the following results on the test dataset:

- **Accuracy:** 87.5%
- **Precision:** 85.3%
- **Recall:** 86.8%
- **F1-Score:** 86.0%

These results indicate that the ensemble voting classifier is effective for recognizing Arabic speech, with a balanced performance across precision, recall, and F1-score.

## Future Work

- **Deep Learning:** Experiment with deep learning models like CNNs or RNNs for improved accuracy.
- **Real-Time Recognition:** Implement real-time speech recognition using streaming audio data.
- **Dataset Expansion:** Use a larger and more diverse Arabic speech dataset to improve the model's generalization.
- **Mobile App Enhancements:** Improve the user interface of the Android app and add more features such as real-time feedback during recitation.

## Contributing

Contributions are welcome! Please fork this repository and submit a pull request for any features or improvements you'd like to add.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
