# Image-Captioning

**Training a CNN-RNN model to predict captions for a given image**

This project implements an encoder–decoder architecture using Convolutional Neural Networks (CNN) as the encoder and Recurrent Neural Networks (RNN) with LSTM cells as the decoder to generate natural language captions from images. The model is trained using the COCO dataset.

---

## Project Overview

- **Encoder**: Extracts image features using a CNN (e.g., pre-trained ResNet or VGG).  
- **Decoder**: Generates captions using an LSTM-based RNN, taking the CNN features as initial input.  

The repository contains Jupyter notebooks and Python scripts covering the full pipeline—from preliminary exploration to inference.

---

## Repository Structure

- **0_Dataset.ipynb** — Data loading and preprocessing  
- **1_Preliminaries.ipynb** — Exploratory data analysis and setup  
- **2_Training.ipynb** — Model training and learning curves  
- **3_Inference.ipynb** — Generating captions for new images  
- **4_Zip Your Project Files and Submit.ipynb** — Packaging for submission  
- **data_loader.py** — Loads and preprocesses COCO dataset  
- **model.py** — Defines the CNN-RNN model architecture  
- **vocabulary.py** — Manages text tokenization and vocabulary  
- **vocab.pkl** — Serialized vocabulary object  
- **README.md** — This file  

---

## Datasets

- Uses the **COCO (Common Objects in Context)** dataset for training and evaluation.  
- Ensure you download and structure the dataset as expected by the data loader (see `0_Dataset.ipynb` for guidance).  

---

## Getting Started

### Prerequisites

Install required dependencies (e.g., TensorFlow or PyTorch, NumPy, etc.):

pip install -r requirements.txt


---

## Workflow

Prepare the Data: Run 0_Dataset.ipynb to download and preprocess images and captions.

Explore & Set Up: Use 1_Preliminaries.ipynb to explore data distributions, vocabulary, and image samples.

Train the Model: Run 2_Training.ipynb to train the CNN–LSTM model. Monitor training loss and evaluation metrics.

Generate Captions: Use 3_Inference.ipynb to load a trained model and generate captions for new images.

Submission Packaging: Optionally, 4_Zip Your Project Files and Submit.ipynb helps package the project for submission or sharing.


---


## Results & Sample Output

Once trained, the model should be able to generate captions like:

"A group of people standing on a beach holding surfboards."

You can find example outputs in the notebooks (e.g., 3_Inference.ipynb).


---

## Acknowledgements

COCO Dataset for rich image-caption pairs.

Inspired by the classic encoder–decoder architecture (CNN → LSTM) often used in image captioning.


---
-
## Contact & Contributions


- Author: Hamid Ghasemi

- Feel free to open issues or submit pull requests for enhancements or bug fixes.
















