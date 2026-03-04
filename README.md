# 📘 Patronizing and Condescending Language Detection (PCL)

## 🎯 Project Description

This project focuses on detecting Patronizing and Condescending Language (PCL) using a fine-tuned RoBERTa-base transformer model.

The objective is to classify text paragraphs into:

- PCL (Patronising / Condescending Language)
- Non-PCL

PCL detection is a challenging Natural Language Processing (NLP) task because patronising language is often subtle and context-dependent.

The model was developed using the **Don’t Patronize Me! dataset**.

---

## 🧠 Methodology

The approach is based on task-specific fine-tuning of a pretrained RoBERTa encoder.

Pipeline steps include:

- Text preprocessing and normalization
- Dataset splitting into training, validation, and dev sets
- Data augmentation via back-translation
- Random oversampling for class imbalance mitigation
- Custom neural classification head

The classification head consists of:

- Linear projection layer
- ReLU activation function
- Dropout regularisation (0.3 rate)
- Binary classification output layer

Training uses:

- AdamW optimizer
- Weight decay regularisation
- Exponential learning rate scheduler

---

## 📊 Evaluation

Metrics used:

- Confusion Matrix
- Precision–Recall Curve
- Average Precision (AP) Score
- Recall, Precision, F1-score

### Performance on Dev Set

- Class 1 Precision: **0.50**
- Class 1 Recall: **0.64**
- Class 1 F1-score: **0.56**
- Macro F1-Score: **0.75**
- Average Precision Score (AP): **0.584**

---

## 📁 Repository Structure

```
📦DontPatronizeMe
 ┣ 📂BestModel/                    # Final model code
 ┣ 📂Predictions/                 # Prediction outputs (dev/test)
 ┣ 📂dataset/                     # Dataset preprocessing & splits
 ┣ 📂models/                      # Model definitions from hyperparameter tuning
 ┣ 📂train_data/                  # Training data
 ┣ 📂test_data/                   # Test data
 ┣ 📂other-notebooks/             # Experiment notebooks - includes EDA
 ┣ 📜README.md                   # This file
 ┗ 📜.gitignore
```


---

## 💻 Setup and Running Instructions

### ⭐ Google Colab (Recommended)

Open the notebook:

```
final-model.ipynb
```

Then run cells sequentially.

The notebook installs required packages automatically.

---

### ⭐ Local Environment (Alternative to Colab)

If not running on Google Colab, install dependencies manually:

```bash
pip install torch torchvision transformers
pip install nlpaug sacremoses nltk
pip install scikit-learn matplotlib seaborn imbalanced-learn
```

Then download dataset files and run:

jupyter notebook final.ipynb
📦 Key Libraries Used

PyTorch

HuggingFace Transformers

Scikit-learn

Matplotlib / Seaborn

NLTK

Imbalanced-learn

📈 Model Evaluation Visualisations

The project includes:

Confusion matrix heatmap

Precision–Recall curve analysis

Classification report metrics

🔬 Research Notes

The model was trained specifically for detecting subtle forms of patronizing language.

Class imbalance was handled using oversampling techniques.

👤 Author

Tabeer Asif
