# Multimodal Disaster Information Classification and Prioritization

## Table of Contents


- [About The Project](#About-The-Project)
- [Background](#Background)
- [Getting Started](#install)
- [Usage](#usage)
- [API Reference](#api-reference)
- [Contributing](#contributing)


## About The Project

This project applies multimodal machine learning to social media posts about disasters, combining tweet **text** and accompanying **images** to:
- Detect whether the post is **Informative** or **Uninformative**
- Classify whether it relates to **Humanitarian** needs

This project supports the following SDGs:

- SDG 3 - Good Health and Well-being
- SDG 9 – Industry, Innovation and Infrastructure
- SDG 11 – Sustainable Cities and Communities
- SDG 16 – Peace, Justice and Strong Institutions


## Background

This project addresses the challenge of prioritizing crisis-related social media data by fusing textual and visual content. 

This projecty uses:
- **ResNet152** for image embedding
- **BERT** for text embeddding
- **VisualBERT** for multimodal fusion and classification

Datasets used in this project are:
- [CrisisMMD2INF](https://huggingface.co/datasets/xiaoxl/crisismmd2inf)
- [CrisisMMD2HUM](https://huggingface.co/datasets/xiaoxl/crisismmd2hum)

## Getting Started

You will need Python 3.8+ and pip if you will run this locally. 

Then install dependencies:

  ```sh
  pip install torch torchvision transformers datasets scikit-learn pandas numpy
  ```

## Usage

To use this project:

1. Clone this repository.
2. Open the notebook in your desired notebook environment.
3. Run each cell to:
   - Load and preprocess the data
   - Extract image and text features
   - Train with VisualBERT
   - Evaluate performance (Accuracy, Loss, Precision, Recall, and F1-Score)



## API Reference

This project is implemented in a single Jupyter notebook. It does not expose a standalone API, but includes the following core components:

 - **Image Encoders**
   - **ResNet-50**  
  Source: `torchvision.models.resnet50`  
  Role: Baseline CNN for image feature extraction

   - **ResNet-152**  
  Source: `torchvision.models.resnet152`  
  Role: Deeper CNN model used for enhanced image feature representation

   - **DINO-ViT**  
  Example model: `facebook/dino-vits16` via Hugging Face Transformers  
  Role: Self-supervised Vision Transformer for advanced image understanding

- **Text Encoder**
  - **BERT Base Uncased**  
  Model: `bert-base-uncased` from Hugging Face  
  Role: Tokenization and embedding of tweet text

- **Multimodal Model**
  - **VisualBERT**  
  Model: `uclanlp/visualbert-vqa-coco-pre`  
  Role: Combines text and image embeddings for multimodal classification

## Contributing

Feel free to open issues or submit pull requests. Contributions that improve accuracy, efficiency, or functionality are welcome!