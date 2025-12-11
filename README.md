# Detecting Mycobacterium Tuberculosis from Smear Microscopy

**Authors:** Joshua Foster, Sophia Godfrey, Adam Brewster, and Landon Amick

## Project Overview
Tuberculosis (TB) remains a leading cause of death from infectious diseases worldwide. Traditional diagnosis via smear microscopy is time-consuming and error-prone, relying heavily on the subjective skill of laboratory technicians.

This project implements and compares Deep Learning architectures to automate the detection of *Mycobacterium tuberculosis* bacilli in smear microscopy images. We evaluated a custom Convolutional Neural Network (CNN) against a residual network (ResNet-10), explored transfer learning with classical machine learning models, and performed extensive hyperparameter tuning to ensure clinical reliability.

## Repo Structure

### Data Directory
* **`DDS/`**: Contains the full dataset of smear microscopy images.
  * **`NP/IMAGE/`**: Negative (Healthy) sample images.
  * **`PP/IMAGE/`**: Positive (TB) sample images.

### Notebooks & Source Code
1. **`BaseCNN.ipynb`**
   * **Purpose:** Establishes the baseline performance using a standard sequential CNN.
   * **Feature Extraction:** This notebook also trains the CNN to act as a feature extractor. It truncates the classification head and exports the learned 128-dimensional feature vectors to be used by classical models.

2. **`Classical_Models.ipynb`**
   * **Purpose:** Evaluates classical machine learning algorithms (Support Vector Machine, Random Forest, Logistic Regression) using the features extracted by the BaseCNN.

3. **`CNN_Revision.ipynb`**
   * **Purpose:** The experimental laboratory. This notebook conducts a comparative study between the Custom CNN and ResNet-10 across varying dropout rates (0.1 - 0.5).

4. **`ResNet10.ipynb`**
   * **Purpose:** This notebook contains the optimized, reproducible run of the best-performing architecture (ResNet-10, Dropout 0.2) trained for 30 epochs with fixed random seeds.

## Dataset
The dataset consists of **31,484** patches of smear microscopy images.
* **Image Size:** 40x40 pixels (RGB)
* **Preprocessing:** Images are normalized to [0,1] range.


## Installation & Usage
1. **Clone the repository:**
   ```bash
   git clone https://github.com/jfoste81/Mycobacterium-Tuberculosis-Classifier
   ```

2. **Install Dependencies** 
   ```bash
   numpy
   pandas
   opencv-python
   scikit-learn
   tensorflow
   matplotlib
   seaborn
   scipy
   ipywidgets
   ```