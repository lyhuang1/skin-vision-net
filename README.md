# 🩺 SkinVisionNet: A Computer Vision Sandbox for Skin Disease Classification

SkinVisionNet is an **end-to-end sandbox project** that demonstrates how to build, train, and deploy a **computer vision model** for **skin disease classification**.  

Keywords: **data collection, deep learning, evaluation, cloud deployment, open-source**.

⚠️ **Disclaimer**: This project is for **educational and research purposes only**. The model is **not a medical device** and should not be used for clinical diagnosis.

---

## 📌 Overview of the Problem
Skin diseases such as **eczema, psoriasis, acne, melanoma, and basal cell carcinoma** affect millions worldwide.  
Early detection can improve outcomes, but diagnosis often requires **specialist knowledge**.  

This project explores how **computer vision** can be used to automatically classify skin conditions from images, demonstrating:
- Dataset collection via web scraping
- Deep learning model training
- Performance evaluation
- Cloud deployment for interactive demos

---

## 📊 Dataset Collection
Data is collected from **publicly available sources** such as DermNet NZ and the ISIC Archive (where permissions allow).

Steps:
1. **Web scraping** using `BeautifulSoup` / `selenium`
2. **Data cleaning** (removing duplicates, resizing, validating formats)
3. **Preprocessing** (normalisation, augmentation)
4. **Train/val/test split** (70/15/15)

Example classes:
- `eczema`
- `psoriasis`
- `acne`
- `melanoma`
- `basal cell carcinoma`

📁 See: `notebooks/01_scraping.ipynb` and `data/processed/`

---

## 🧠 Model Architecture
We use **PyTorch** with a **ResNet-18 backbone**, fine-tuned for multi-class classification.

- **Input**: 224×224 RGB images  
- **Backbone**: ResNet-18 (`torchvision.models.resnet18`)  
- **Classifier head**: Fully connected layer with softmax output (5 classes)  
- **Loss function**: CrossEntropyLoss  
- **Optimizer**: Adam + learning rate scheduler  

📁 Implementation: `src/model.py`, `src/train.py`

---

## 📈 Evaluation Results
Example performance (on a small demo dataset):

- Accuracy: **78.4%**
- Precision (avg): **0.80**
- Recall (avg): **0.77**
- F1-score (avg): **0.78**

📊 Visualisations:
- Confusion matrix
- ROC curves
- Class-wise breakdown

📁 See: `notebooks/04_eval.ipynb`

---

## ☁️ Cloud Deployment Options
SkinVisionNet can be deployed in the cloud for **interactive demos**.

### AWS EC2
- Launch GPU instance (p3 or g4dn recommended)  
- Install dependencies (`requirements.txt`)  
- Run Flask chatbot demo (`chatbot/app.py`)  
- Open port `5000` to access demo in browser  

📁 Setup guide: `cloud/aws_setup.md`

### Other Options
- **Hugging Face Spaces** (Gradio / Streamlit demo)  
- **Docker container** for portability  
- **Render / Heroku** for free-tier hosting  

---

## ⚖️ Licensing
This project is released under the **MIT License**.  
See [LICENSE](LICENSE) for details.

⚠️ **Disclaimer**: The model and demo are **not intended for clinical use**. Always consult a licensed medical professional for health concerns.

---

## 📚 Citation
If you use this project in your research or learning, please cite:

```bibtex
@misc{skinvisionnet2025,
  author       = {Huang, Leo},
  title        = {SkinVisionNet: A Computer Vision Sandbox for Skin Disease Classification},
  year         = {2025},
  howpublished = {\url{https://github.com/lyhuang1/skin-vision-net}},
  note         = {Educational and research use only}
}
