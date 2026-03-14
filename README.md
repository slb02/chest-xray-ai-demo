# 🫁 Chest X-Ray AI with Explainability (Grad-CAM + LLM)

🚨 **Educational Use Only — Not for Clinical Diagnosis**

This project demonstrates how a deep learning model analyzes chest X-ray images, highlights salient regions using Grad-CAM, and explains its behavior in plain English.  
It is designed as a **transparent, responsible AI demo** for medical imaging — **not** a diagnostic system.

**Demo link:** https://huggingface.co/spaces/sbathina/chest-xray-xai-demo

---

## 🎯 Project Objective

Medical AI models are often criticized for being *black boxes*.  
This project focuses on **interpretability**, not accuracy bragging.

**Goals:**
- Show how a chest X-ray classification model arrives at predictions.
- Visualize *where* the model looks using Grad-CAM.
- Explain *why* predictions were made in simple, human-readable language.
- Demonstrate responsible AI deployment practices.

---

## 🧠 What This Project Does (End-to-End)

1. User uploads a chest X-ray image  
2. A pretrained deep learning model predicts probabilities for 18 thoracic findings  
3. Grad-CAM highlights image regions most influential for a selected prediction  
4. A language model explains the results in plain English  
5. Clear disclaimers ensure safe, non-clinical usage  

---

## 🖼 Example Output

- Original X-ray image
- Grad-CAM heatmap overlay
- Multi-label probability table
- Human-readable explanation of model behavior

<img width="690" height="777" alt="Screenshot 2026-02-08 at 8 45 43 PM" src="https://github.com/user-attachments/assets/7bd2974b-2e80-4d7d-bc6f-a6cdbb9581c2" />
<img width="690" height="777" alt="Screenshot 2026-02-08 at 8 45 10 PM" src="https://github.com/user-attachments/assets/101ca515-7ac0-4851-9b49-f9adb1f813e2" />


---

## 🏗 Architecture Overview
User Upload
↓
Streamlit UI
↓
DenseNet-121 (TorchXRayVision)
↓
Multi-Label Predictions (18 findings)
↓
Grad-CAM Heatmap
↓
Overlay Visualization
↓
LLM / Fallback Explanation

---

## 🧬 Model Details

- **Architecture:** DenseNet-121
- **Library:** TorchXRayVision
- **Task:** Multi-label chest X-ray classification
- **Training Data (pretrained):**
  - NIH ChestX-ray14
  - CheXpert
  - MIMIC-CXR

**Predicted Findings (18):**
Atelectasis, Cardiomegaly, Consolidation, Edema, Effusion, Emphysema,  
Fibrosis, Fracture, Hernia, Infiltration, Lung Lesion, Lung Opacity,  
Mass, Nodule, Pleural Thickening, Pneumonia, Pneumothorax,  
Enlarged Cardiomediastinum

---

## 🔍 Explainability (Grad-CAM)

Grad-CAM (Gradient-weighted Class Activation Mapping):
- Computes gradients of a target class w.r.t. convolutional feature maps
- Produces a heatmap showing influential image regions
- Helps humans **understand model focus**, not confirm disease

> Important: Highlighted regions **do not indicate pathology** — only model attention.

---

## 🗣 Plain-English Explanation (LLM)

- If **Ollama (local LLM)** is available → explanation is generated locally
- If unavailable → safe, deterministic fallback explanation is used

This avoids:
- Cloud dependency
- Privacy risks
- Hallucinated medical advice

---

## ⚠️ Responsible AI Disclaimer

❌ Not a medical device  
❌ Not FDA approved  
❌ Not for diagnosis or treatment  
✅ Visualization of model behavior only  

---

## 🛠 Tech Stack

| Component | Tool |
|---------|------|
| UI | Streamlit |
| Model | DenseNet-121 |
| Medical ML | TorchXRayVision |
| Explainability | Grad-CAM |
| Image Processing | OpenCV, PIL |
| Language Explanation | Ollama (optional) |
| Deployment | Hugging Face Spaces |

---

## 🚀 Deployment

This app is deployed on **Hugging Face Spaces** as a public demo.

Steps:
1. Push code to GitHub
2. Create a new Hugging Face Space
3. Select **Streamlit**
4. Connect GitHub repo or upload files
5. App builds automatically
   
<img width="1710" height="624" alt="Screenshot 2026-02-08 at 8 48 25 PM" src="https://github.com/user-attachments/assets/28c2bd6a-fb7f-4ae5-8e63-a25355003c94" />
<img width="1709" height="637" alt="Screenshot 2026-02-08 at 8 48 49 PM" src="https://github.com/user-attachments/assets/819e52b1-f035-4816-ab65-11f4b758b012" />

---

## 📜 License

MIT License — for educational and research use only.
