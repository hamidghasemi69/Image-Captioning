<div align="center">

# 🖼️ Image Captioning

**A CNN–RNN model that looks at a photo and writes a sentence describing it**

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" alt="PyTorch">
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter">
  <img src="https://img.shields.io/badge/Udacity-02B3E4?style=for-the-badge&logo=udacity&logoColor=white" alt="Udacity">
</p>

</div>

---

## 📌 Overview

This project combines computer vision and natural language processing: a pretrained **ResNet-50** encoder turns an image into a feature vector, and an **LSTM** decoder generates a caption word by word. The model is trained on the Microsoft **COCO** dataset.

## 🖼️ Results

Example captions generated on test images:

<img width="1291" alt="Image captioning results" src="https://github.com/hamidghasemi69/Image-Captioning/assets/22797186/23200d45-5d6c-48c2-aeb4-bf533b402714">

<img width="376" alt="Image captioning sample" src="https://github.com/hamidghasemi69/Image-Captioning/assets/22797186/ea4e0aa1-657b-4e97-b1b0-4781e4b5f775">

| Metric | Value |
|---|---|
| Final training loss | ≈ 2.2 (cross-entropy) |
| Final perplexity | ≈ 8.8 |
| Training | 3 epochs over ~414k caption–image pairs, batch size 128 |

## 🧠 Architecture

```mermaid
flowchart LR
    I["Image<br/>224×224"] --> E["Encoder<br/>ResNet-50 (frozen)<br/>+ Linear → 256"]
    E --> D["Decoder<br/>Embedding 256 → LSTM 512"]
    D --> L["Linear → vocabulary"]
    L --> C["“a man riding a wave<br/>on a surfboard”"]
```

| Setting | Value |
|---|---|
| Encoder | ResNet-50 pretrained on ImageNet, final layer replaced by a 256-d embedding |
| Decoder | Word embedding (256) → single-layer LSTM (hidden size 512) → linear layer over the vocabulary |
| Vocabulary | Words appearing at least 5 times in the training captions |
| Augmentation | Resize 256 → random crop 224, horizontal flip, ImageNet normalization |
| Optimizer | Adam (lr = 1e-4) on the decoder and the encoder's embedding layer |
| Inference | Greedy sampling, one word at a time until `<end>` |

## 🗂️ Dataset

[Microsoft COCO 2014](https://cocodataset.org/): over 80,000 training images, each with 5 human-written captions.

## 📂 Repository structure

```
├── 0_Dataset.ipynb        # exploring COCO images and captions
├── 1_Preliminaries.ipynb  # data loader, vocabulary and model sanity checks
├── 2_Training.ipynb       # training the encoder–decoder
├── 3_Inference.ipynb      # generating captions for new images
├── data_loader.py         # COCO data loader with caption-length batching
├── vocabulary.py          # builds and stores the word ↔ index vocabulary
├── vocab.pkl              # saved vocabulary
├── model.py               # EncoderCNN and DecoderRNN
└── README.md
```

## 🚀 Getting started

```bash
# 1. Clone the repository
git clone https://github.com/hamidghasemi69/Image-Captioning.git
cd Image-Captioning

# 2. (Recommended) create a virtual environment
python -m venv .venv && source .venv/bin/activate
pip install torch torchvision nltk pycocotools matplotlib jupyter

# 3. Launch the notebook
jupyter notebook
```

Download the [COCO 2014](https://cocodataset.org/#download) images and annotations, then run the notebooks in order (0 → 3).

## 🙏 Acknowledgements

- Project from the **Udacity** Computer Vision Nanodegree
- Vinyals et al., [*Show and Tell: A Neural Image Caption Generator*](https://arxiv.org/abs/1411.4555) (2015)
- [Microsoft COCO](https://cocodataset.org/) dataset

## 👤 Author

**Hamidreza Ghasemi** · Principal Data Scientist @ Arizona State University

[![Website](https://img.shields.io/badge/Website-hamidghasemi69.github.io-2ee6c5?style=flat-square&logo=googlechrome&logoColor=white)](https://hamidghasemi69.github.io)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-hamidghasemi69-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/hamidghasemi69/)
[![GitHub](https://img.shields.io/badge/GitHub-hamidghasemi69-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/hamidghasemi69)

<sub>If you find this project useful, consider giving it a ⭐</sub>
