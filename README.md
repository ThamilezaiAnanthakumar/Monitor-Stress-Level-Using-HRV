
## 🧠 Stress Level Monitoring Using HRV and Neural Networks

### 🔍 **Overview**

This project aims to predict and monitor stress levels (categorized as *interruption*, *no stress*, and *time pressure*) in undergraduate students using Heart Rate Variability (HRV) parameters. It leverages machine learning to improve mental health awareness and personalized feedback through a wearable monitoring device.

---

### 💾 **Dataset & Feature Selection**

* **Dataset Used**: [SWELL-KW Stress Dataset](https://www.kaggle.com/datasets/qiriro/swell-heart-rate-variability-hrv)
* **Input Features**: 35 HRV features (time, frequency, nonlinear domains)
* **Feature Selection**: Top 10 features selected via statistical and ML-based methods (e.g., correlation, PCA, or mutual information)

---

### 🤖 **Machine Learning Model**

* **Model Used**: Neural Network (NN)
* **Training Input**: Selected 10 HRV features
* **Output**: One of three stress states –

  * `Interruption`
  * `No Stress`
  * `Time Pressure`

---

### 🛠 **Hardware Implementation**

* **Microcontroller**: ESP32 s3 Wroom 1 N16
* **Sensors**:

  * **ECG** (single-lead): Captures accurate R-peaks
  * **PPG**: Wearable-friendly; ideal for wristband/watch
* **Signal Processing**:

  * Peak detection and HRV extraction using `NeuroKit2`
  * Local model inference (on-device prediction)

---

### 🧬 **HRV Features Used (Example Subset)**

* Mean RR, RMSSD, pNN50 (Time-domain)
* VLF (Frequency-domain)
* SD2, Higuchi (Nonlinear)

---

### 🗂️ **Modular Processing Pipeline**

```text
[Sensor (ECG/PPG)]
       ↓
[Peak Detection (NeuroKit2)]
       ↓
[HRV Feature Extraction]
       ↓
[10-Feature Selection Pipeline]
       ↓
[Neural Network Classifier]
       ↓
[Stress Level Output]
       ↓
[Feedback to User ]
```

---

### 📊 **Flowchart (Conceptual)**

1. **Signal Acquisition**

   * ECG or PPG captured via sensor
2. **Preprocessing**

   * Noise removal, peak detection
3. **Feature Extraction**

   * HRV parameters calculated (time/frequency/nonlinear)
4. **Feature Selection**

   * Top 10 most predictive features extracted
5. **Prediction**

   * Neural network infers stress category
6. **Output & Feedback**

   * Real-time monitoring 

---

### 🧠 **Goal**

Support students' mental health by:

* Continuously monitoring stress
* Offering real-time insights and advice
* Enabling academic institutions to act proactively


