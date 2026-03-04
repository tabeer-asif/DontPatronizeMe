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
1. Upload the repository to Google Drive or connect GitHub to Colab.
2. Open the notebook:
```
final-model.ipynb
```
3. Dataset files are already included inside the repository under:

```
dataset
```
4. The trained model is stored externally due to file size limitations.

👉 Download the model from the provided Google Drive link and place it in:

```
BestModel/
```
(or update the model loading path inside the notebook)

Run notebook cells sequentially.

The notebook automatically installs required dependencies.

---

### ⭐ Local Environment (Alternative to Colab)

1. Clone Repository
```
git clone https://github.com/tabeer-asif/DontPatronizeMe.git
cd DontPatronizeMe
```
2. Install dependencies

```bash
pip install torch torchvision transformers
pip install nlpaug sacremoses nltk
pip install scikit-learn matplotlib seaborn imbalanced-learn
```
3. Download Model

Download the pretrained model from the Google Drive link provided in the project documentation.

Place the model files inside:
```
BestModel/
```
Update model loading paths in ```final-model.ipynb``` if necessary.

4. Launch Notebook
```
jupyter notebook final-model.ipynb
```

Run cells sequentially.

## References

1. Pérez-Almendros, Carla, Luis Espinosa Anke, and Steven Schockaert. "Don't Patronize Me! An Annotated Dataset with Patronizing and Condescending Language towards Vulnerable Communities." *Proceedings of the 28th International Conference on Computational Linguistics (COLING 2020)*.

2. Pérez-Almendros, Carla, Luis Espinosa Anke, and Steven Schockaert. "SemEval-2022 task 4: Patronizing and condescending language detection." *Proceedings of the 16th International Workshop on Semantic Evaluation (SemEval-2022)*.

3. Liu, Yinhan, et al. "RoBERTa: A Robustly Optimized BERT Pretraining Approach." *arXiv preprint arXiv:1907.11692* (2019).

4. Dataset: https://github.com/Perez-AlmendrosC/dontpatronizeme

## 👤 Author

Tabeer Asif

# License

This project is for educational and research purposes.
