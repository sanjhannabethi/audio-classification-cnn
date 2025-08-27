# 🎵 Audio Classification with ResNet-style CNNs

An audio classification CNN trained and deployed from scratch, that **classifies environmental sounds from the ESC-50 dataset into 50 categories** using a ResNet-based CNN trained on Mel Spectrograms. 

The model will classify sounds like a dog barking or birds chirping from an audio file. This project uses advanced techniques like **Residual Networks (ResNet), data augmentation, mixing, and Mel Spectrograms** to build a robust training pipeline.

The project includes a **Modal cloud-deployed inference FastAPI inference service** and a **Next.js frontend** to upload audio & visualize the model's predictions and internal CNN layer feature maps to see what it "sees".

---

## 🚀 Tech Stack

- **Dataset** – [ESC-50: Dataset for Environmental Sound Classification](https://github.com/karolpiczak/ESC-50)
- **Python (PyTorch)** – Model architecture & training  
- **Librosa / Torchaudio** – Audio preprocessing (waveform --> Mel spectrogram)  
- **FastAPI** – Inference API
- **Modal** – Serverless cloud GPU training + deployment  
- **TensorBoard** – Training logs & visualization
- **Next.js + Tailwind CSS** – Frontend visualization & dashboard  
---

## ✨ Features

- Trained a **Deep Audio CNN** for real-time sound classification with confidence scores
- **ResNet-style architecture with residual blocks** with batch normalization and shortcuts for stable and fast training
- Achieved **~84.5% accuracy** on the ESC-50 dataset  
- Converts raw audio into **Mel spectrograms** (image) for CNN input 
- Data augmentation with Mixup & Time/Frequency Masking
- Optimized training with AdamW & OneCycleLR scheduler
- TensorBoard integration for training analysis
- Serverless GPU inference with Modal
- Deployed inference as a **FastAPI inference endpoint using Modal**  
- Interactive Next.js & React dashboard with frontend visualizations:
  - 🎵 Uploaded audio waveform  
  - 🎼 Input spectrogram  
  - 📈 CNN intermediate feature maps (heatmaps)  
  - 📊 Prediction probabilities  

---

## 📂 Project Structure

```
.
├── audio-cnn-visualization/   # Next.js frontend for visualization
│   ├── src/app/               # Pages & app layout
│   ├── src/components/        # UI components (Waveform, FeatureMap, ColorScale)
│   ├── public/                # Static assets (icons, logos, sample images)
│   └── package.json
│
├── model.py                   # ResNet-based CNN architecture
├── train.py                   # Training pipeline (ESC-50 dataset, spectrogram conversion)
├── inference.py               # FastAPI inference service (deployed on Modal)
├── main.py                    # Entry point
├── requirements.txt           # Python dependencies
├── chirpingbirds.wav          # Sample audio clip
└── README.md
```

---

## 🚀 Getting Started (Project Setup)

Follow these steps to install and set up the project.

### Clone the Repository
```bash
https://github.com/sanjhannabethi/audio-classification-cnn.git
```

### Install Python

Download and install Python if not already installed. Use the link below for guidance on installation: [Python Download](https://www.python.org/downloads/)

Create a virtual environment with Python 3.12.

### Backend

Navigate to folder:
```bash
cd audio-cnn
```

Install dependencies:
```bash
pip install -r requirements.txt
```

Modal setup:
```bash
modal setup
```

Run on Modal:
```bash
modal run main.py
```

Deploy backend:
```bash
modal deploy main.py
```

### Frontend

Install dependencies:
```bash
cd audio-cnn-visualisation
npm i
```
Run:
```bash
npm run dev
```
