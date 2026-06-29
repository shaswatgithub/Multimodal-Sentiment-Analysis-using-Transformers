# 🎭 Multimodal Sentiment Analysis using BERT and Vision Transformer (ViT)

A deep learning project that performs **multimodal sentiment analysis** by combining **text** and **image** information. The model leverages **BERT** for textual feature extraction and **Vision Transformer (ViT)** for image feature extraction, then fuses both representations for sentiment classification.

---

## 📌 Overview

Traditional sentiment analysis relies only on textual information. However, social media posts, reviews, and online content often contain both **text and images**, where the visual context significantly influences sentiment.

This project implements a multimodal neural network that:

- Extracts text embeddings using **BERT**
- Extracts image embeddings using **Vision Transformer (ViT)**
- Combines both feature vectors
- Classifies sentiment using fully connected layers

---

## 🚀 Features

- Multimodal sentiment classification
- BERT-based text encoder
- Vision Transformer (ViT) image encoder
- Feature fusion using concatenation
- PyTorch implementation
- GPU support (CUDA)
- Easy to train on custom datasets

---

## 🏗️ Model Architecture

```
                Text Input
                     │
              BERT Tokenizer
                     │
                BERT Encoder
                     │
             Text Feature Vector
                     │
                     ├───────────────┐
                     │               │
                     │      Concatenation
                     │               │
Image Input          │               │
     │               │               │
ViT Feature Extractor│               │
     │               │               │
 Vision Transformer Encoder          │
     │                               │
Image Feature Vector──────────────────┘
                     │
              Fully Connected Layer
                     │
                 Dropout
                     │
            Sentiment Classifier
                     │
          Positive / Neutral / Negative
```

---

## 📂 Project Structure

```
Multimodal-Sentiment-Analysis/
│
├── dataset/
│   ├── images/
│   └── multimodal_sentiment_data.csv
│
├── notebooks/
│   └── Multimodal_Sentiment_Analysis.ipynb
│
├── models/
│   └── trained_model.pt
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

## 📊 Dataset Format

The CSV file should contain the following columns:

| text | image_path | label |
|------|------------|--------|
| I love this product! | images/img1.jpg | Positive |
| Very disappointing | images/img2.jpg | Negative |
| It's okay | images/img3.jpg | Neutral |

Example:

```csv
text,image_path,label
Amazing experience!,images/1.jpg,Positive
Worst purchase ever,images/2.jpg,Negative
Average quality,images/3.jpg,Neutral
```

---

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/Multimodal-Sentiment-Analysis.git

cd Multimodal-Sentiment-Analysis
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Or install manually:

```bash
pip install transformers datasets torch torchvision sentencepiece scikit-learn pandas pillow
```

---

## ▶️ Running the Project

Place your dataset in the project folder.

Run the notebook or Python script:

```bash
python train.py
```

or

Open the notebook in Google Colab and execute all cells.

---

## 🧠 Pretrained Models Used

### Text Encoder

- BERT Base Uncased
- Hidden Size: 768

### Image Encoder

- Google Vision Transformer (ViT Base Patch16-224)
- Hidden Size: 768

Combined Feature Size:

```
768 + 768 = 1536
```

These features are passed through fully connected layers for final classification.

---

## 🔄 Training Pipeline

1. Load dataset
2. Encode labels
3. Tokenize text using BERT tokenizer
4. Process images using ViT feature extractor
5. Create PyTorch Dataset
6. Train BERT + ViT fusion model
7. Validate model
8. Compute accuracy

---

## 📈 Evaluation Metric

The project currently evaluates using:

- Accuracy Score

Future improvements can include:

- Precision
- Recall
- F1 Score
- Confusion Matrix
- ROC-AUC

---

## 📦 Technologies Used

- Python
- PyTorch
- Hugging Face Transformers
- BERT
- Vision Transformer (ViT)
- Scikit-learn
- Pandas
- Pillow

---

## 💻 Hyperparameters

| Parameter | Value |
|------------|-------|
| Batch Size | 8 |
| Learning Rate | 2e-5 |
| Epochs | 3 |
| Max Text Length | 128 |
| Optimizer | AdamW |
| Loss Function | CrossEntropyLoss |

---

## 📸 Example Workflow

```
Text
 ↓
BERT
 ↓
Text Embedding

Image
 ↓
ViT
 ↓
Image Embedding

Text + Image
 ↓
Feature Fusion
 ↓
Classifier
 ↓
Sentiment Prediction
```

---

## 🔮 Future Improvements

- Attention-based multimodal fusion
- CLIP-based multimodal embeddings
- RoBERTa or DeBERTa support
- Data augmentation
- Early stopping
- Learning rate scheduler
- TensorBoard logging
- Model checkpointing
- Explainable AI (Grad-CAM & Attention Visualization)
- Deployment using Streamlit or Flask

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a new feature branch
3. Commit your changes
4. Push the branch
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License.

---

## 👨‍💻 Author

**Your Name**

GitHub: https://github.com/yourusername

LinkedIn: https://linkedin.com/in/yourprofile

---

## ⭐ Support

If you found this project helpful, please consider giving it a **⭐ Star** on GitHub.
