# RepAIr: AI-Powered Intelligent Repair Assistant

![React Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
![Render](https://img.shields.io/badge/Render-46E3B7?style=for-the-badge&logo=render&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)

> **RepAIr** is a cross-platform intelligent repair assistant that leverages Natural Language Processing (NLP) to transform unstructured repair documentation into actionable, step-by-step intelligence.

The system addresses the challenge of complex, scattered repair manuals by providing an intelligent interface for question answering, anomaly detection, and part recommendations. By democratizing access to repair knowledge, this project directly supports the **Right to Repair** movement and Sustainable Development Goals (SDG 9, 12, and 4).

---

## 🚀 Live Deployment

The backend infrastructure is fully deployed and hosted on **Render**.

* **Backend Base URL:** `https://repair-1-on.render.com`
* **Status:** Active (99.7% Uptime)
* **Documentation:** `https://repair-1-on.render.com/docs`

---

## 🌟 Key Features

* **🤖 Intelligent Q&A Assistant:** Uses a fine-tuned **FLAN-T5-small** model to generate structured, step-by-step repair instructions with 89.1% semantic similarity.
* **⚠️ Anomaly Detection:** Identifies gaps, inconsistencies, or logical errors in repair documentation using **Sentence-BERT** and **Isolation Forest** with 87.3% precision.
* **🔧 Part Recommendation Engine:** Delivers sub-millisecond retrieval of relevant tools and parts using **FAISS** (Facebook AI Similarity Search).
* **📱 Cross-Platform Experience:** A responsive **React Native** application (iOS/Android) featuring a unified "purple circuit board" theme.
* **🎥 Multimedia Integration:** Native video playback for repair demonstrations utilizing **Expo AV** with support for `.mov` formats.
* **🌐 Multi-Language Support:** Accessibility features including language preference selection for diverse user populations.

---

## 🛠️ Technology Stack

### Backend (Deployed on Render)
* **Framework:** FastAPI 0.95.0
* **Server:** Uvicorn 0.22.0
* **Language:** Python 3.8+
* **Infrastructure:** Render Cloud Platform (Automatic HTTPS, Auto-deploy from Git)

### Mobile Application (Frontend)
* **Framework:** React Native 0.72.6 with Expo SDK ~49.0.15
* **Navigation:** React Navigation (Stack)
* **Networking:** Axios (with interceptors for loading states)
* **Multimedia:** Expo AV and React Native Video

### AI & Machine Learning
* **Models:** FLAN-T5-small, Sentence-BERT (all-MiniLM-L6-v2)
* **Libraries:** PyTorch, Transformers, Scikit-learn, FAISS-GPU
* **Hosting:** Hugging Face Spaces (for model weights and inference)

---

## ⚙️ System Architecture

The system follows a modular client-server architecture:

1.  **Mobile Client:** Handles user interaction, device selection, and results display.
2.  **API Gateway (Render):** FastAPI backend receives requests, validates input using Pydantic, and routes to specific AI models.
3.  **Inference Layer:**
    * **Q&A:** Generates formatted steps.
    * **Anomaly:** Flags outliers in documentation steps.
    * **Recommendation:** Performs vector similarity search for parts.

---

## 📦 Installation and Setup

### Prerequisites
* **Node.js** (v16.x or higher)
* **Python** (v3.8 or higher)
* **Expo CLI** & **EAS CLI**

### 1. Backend Setup (Local)

Clone the repository and navigate to the backend directory.

```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run the server locally
uvicorn main:app --host 0.0.0.0 --port 8000


