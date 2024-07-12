# Laryngeal Cancer Detection Model (Audio Classifier)

This repository contains the code for a laryngeal audio classification model developed to classify audio samples of the vowel /a/ from male subjects aged 42-75. The dataset includes variations in pitch and distinguishes between healthy individuals and those diagnosed with Stimmlippenkarzinom.

## Dataset

The dataset is sourced from [StimmDB](https://stimmdb.coli.uni-saarland.de/index.php4#target). The dataset details are as follows:

- **Healthy**: 37 male subjects, 4 pitch variations each (neutral, high, low, low-high-low), total 148 samples.
- **Stimmlippenkarzinom**: 21 male subjects, 4 pitch variations each, total 84 samples.

*Note: Testing with female data was not possible due to insufficient data.*

## Preprocessing

The following preprocessing techniques were applied to the audio data:
- Time Stretching
- Time Masking
- Frequency Masking
- Resampling (in one experiment)

## Feature Extraction

The features extracted from the audio samples include:
- MFCC
- Chroma
- Mel-Spectrogram
- Spectral Contrast
- Tonnetz
- Zero Crossing Rate

## Models and Results

The classification models used and their respective accuracies are as follows:

| Preprocessing | Features | Classification Method | Accuracy |
|---------------|----------|-----------------------|----------|
| Time Stretching + Time Masking + Frequency Masking | MFCC + Chroma + Mel-Spectrogram + Spectral Contrast + Tonnetz + Zero Crossing Rate | Logistic Regression | 97.85% |
| Time Stretching + Time Masking + Frequency Masking | MFCC + Chroma + Mel-Spectrogram + Spectral Contrast + Tonnetz + Zero Crossing Rate | Random Forest Classifier | 96.77% |
| Time Stretching + Time Masking + Frequency Masking | MFCC + Chroma + Mel-Spectrogram + Spectral Contrast + Tonnetz + Zero Crossing Rate | Support Vector Classifier | 94.62% |
| Time Stretching + Time Masking + Frequency Masking | MFCC + Chroma + Mel-Spectrogram + Spectral Contrast + Tonnetz + Zero Crossing Rate | SincNet + DNN | 99.14% |
| Time Stretching + Time Masking + Frequency Masking + Resampling | MFCC + Chroma + Mel-Spectrogram + Spectral Contrast + Tonnetz + Zero Crossing Rate | SincNet + DNN | 89.67% |
| Time Stretching + Time Masking + Frequency Masking | MFCC | SincNet + DNN | 96.5% |
| Time Stretching | MFCC | DNN | 100% |

## Usage

### Prerequisites

- Python 3.7+
- Required Python packages

### Installation

Clone the repository and install the required packages

## Author
This project is developed by [Jashanpreet Singh Salh](https://github.com/JASHANPREETSINGHSALH)
