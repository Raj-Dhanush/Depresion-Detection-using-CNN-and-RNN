# 🎧 Speech-Based Depression Detection Using Deep Learning

*A Comparative Study of CNN-BiLSTM and RNN-BiLSTM Architectures with Multiple Audio Feature Representations*

---

## 🔍 Overview

This project focuses on detecting signs of depression using **raw human speech**. Depression often impacts vocal characteristics such as tone, energy, pauses, and articulation. By applying deep learning to speech signals, this project attempts to classify speakers into:

* **Depressed 😔**
* **Not Depressed 🙂**

The system supports both:

* `Offline predictions` using `.wav` audio files
* `Real-Time inference` using live microphone input

---

## 🧪 Dataset

* **Dataset:** DAIC-WOZ (Depression Audio Interview Dataset)
* Contains clinical interview recordings along with PHQ-8 labels.
* Data used only under ethical permission.

> ⚠️ Dataset is not included in this repository due to licensing restrictions.

---

## 🧠 Models Implemented

To understand how architecture and feature choice affect depression detection, six model configurations were tested:

| Feature Type            | CNN + BiLSTM | RNN + BiLSTM |
| ----------------------- | ------------ | ------------ |
| **MFCC**                | ✔ Tested     | ✔ Tested     |
| **Mel-Spectrogram**     | ✔ Tested     | ✔ Tested     |
| **Log-Mel Spectrogram** | ✔ Tested     | ✔ Tested     |

Each experiment used:

* Adam optimizer
* Binary cross-entropy loss
* Early stopping
* Sequence-based learning on overlapping speech frames

---

## 🎚 Feature Engineering

Three audio feature extraction techniques were used:

| Feature Type            | Description                          | Why Used                               |
| ----------------------- | ------------------------------------ | -------------------------------------- |
| **MFCC**                | Represents human hearing perception  | Best for emotional tone & vocal traits |
| **Mel Spectrogram**     | Time-frequency heatmap on mel scale  | Good for CNN feature locality          |
| **Log-Mel Spectrogram** | Mel spectrogram with log compression | Highlights subtle low-energy signals   |

---

## 📈 Experimental Results

Key findings from the experiments:

* **CNN-BiLSTM consistently performed better** than RNN-BiLSTM.
* **MFCC + CNN-BiLSTM achieved the highest F1-score and stability.**
* Spectrogram-based models worked, but were more sensitive to noise and overfitting.
* RNN-based models required longer training and showed less generalization.

📌 **Best Model:**

> **MFCC + CNN-BiLSTM — Best balance of accuracy, recall, and F1-Score**

---

## 🧬 Why CNN-BiLSTM?

| Component          | Contribution                                                       |
| ------------------ | ------------------------------------------------------------------ |
| **CNN Layers**     | Extract spectral texture patterns (pitch shifts, pauses, formants) |
| **BiLSTM Layers**  | Capture temporal emotional progression across speech               |
| **Sigmoid Output** | Binary probability of depression                                   |

This hybrid approach leverages both **acoustic structure** and **speech dynamics**.

---

## 🖥️ Real-Time Prediction

The final system supports:

✔ Running the trained model on `.wav` samples
✔ Live mic inference (record → feature extract → predict)
✔ Saving model checkpoints for reusable inference

Example output:

```
Prediction: Depressed 😔  
Confidence: 0.841
```

---

## 🛠️ Tech Stack

* Python
* PyTorch
* Librosa
* Numpy / Pandas
* SoundDevice (for live mic inference)

---

## 🚀 Future Work

* ⭐ Transformer-based models (Wav2Vec2, Whisper embeddings)
* ⭐ Improved data augmentation (noise, emotion variation)
* ⭐ Multimodal fusion (Text + Audio + Facial Emotion)
* ⭐ Edge deployment for real-time screening applications

---

## 📚 Credits

* Dataset: DAIC-WOZ
* Research conducted as part of a Deep Learning academic project
* Work by: **M. Raj Dhanush & Team**

---


