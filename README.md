# Action-Dection-Model


## Environment Setup and Running the Notebook (TensorFlow 2.20)

This project is tested and verified with the environment configuration below. **All versions are pinned to ensure TensorFlow 2.20 runs correctly inside Jupyter Notebook.**

### Environment Requirements

| Component  | Version  |
| ---------- | -------- |
| Python     | 3.10     |
| TensorFlow | 2.20.0   |
| MediaPipe  | 0.10.9   |
| Protobuf   | 3.20.3   |
| NumPy      | 2.1.3    |
| OpenCV     | 4.5.5.64 |
| IPython    | 8.30.0   |

---

## Conda Environment Setup

All steps below must be executed in **Anaconda Prompt** or **Conda Prompt**.

### Step 1: Create Conda Environment

```bash
conda create -n action-detection python=3.10
```

### Step 2: Activate the Environment

```bash
conda activate action-detection
```

### Step 3: Upgrade pip

```bash
python -m pip install --upgrade pip
```

### Step 4: Install Required Packages

Install dependencies with **exact versions**:

```bash
pip install \
tensorflow==2.20.0 \
mediapipe==0.10.9 \
protobuf==3.20.3 \
numpy==2.1.3 \
opencv-python==4.5.5.64 \
ipython==8.30.0 \
notebook
```

---

## Running `Action Detection.ipynb`

The notebook must be run **sequentially from top to bottom**. Skipping steps will cause errors.

### Step 1: Launch Jupyter Notebook

From the project root directory:

```bash
jupyter notebook
```

A browser window will open at:

```
http://localhost:8888
```

---

### Step 2: Open the Notebook

* Open `Action Detection.ipynb`
* Ensure the kernel is set to **Python 3.10 (action-detection)**

  * Kernel → Change Kernel → Python 3.10

---

## Notebook Execution Guide

### Step 3: Import Dependencies

**Notebook Section:** Import and setup

* Run all import cells.
* Confirm no import errors for TensorFlow, MediaPipe, or OpenCV.

---

### Step 4: Initialize MediaPipe Holistic Model

* Initializes pose, face, and hand landmarks.
* Defines helper functions for drawing landmarks and extracting keypoints.
* No user interaction required.

---

### Step 5: Optional Real-Time Camera Test

* Opens webcam to verify MediaPipe detection.
* Confirm landmarks appear correctly.
* Press `q` to close the camera window.

---

### Step 6: Create Data Collection Folders

* Automatically creates directories for each action and sequence.
* Actions and dataset size are defined in this section.
* Run all cells once before data collection.

---

### Step 7: Collect Action Data (Required)

This is an **interactive step**.

* Webcam opens.
* On-screen prompts indicate:

  * Action name
  * Sequence number
  * Frame countdown
* Perform each action consistently during recording.
* Keypoints are saved automatically as `.npy` files.

Do not interrupt this process. Press `q` only after all actions and sequences are collected.

---

### Step 8: Preprocess Data

* Loads saved keypoints.
* Creates feature arrays (`X`) and encoded labels (`y`).
* No user input required.

---

### Step 9: Train the LSTM Model

* Builds and trains an LSTM-based neural network.
* Training time depends on dataset size and hardware.
* Ensure all previous steps completed successfully.

---

### Step 10: Model Evaluation and Real-Time Prediction (If Included)

* Uses webcam input for live action prediction.
* Perform trained actions to observe model output.

---

## Important Notes

* Always run the notebook in order.
* If you change or add actions, you must re-collect data and retrain the model.
* Python 3.11+ is not supported for TensorFlow 2.20.
* Keep camera position and lighting consistent during data collection.

---

