# Captcha Solver 🧠

A Python-based CAPTCHA solver leveraging computer vision and/or deep learning to automatically decipher various CAPTCHA types using OpenCV, PyTorch, TensorFlow, or similar frameworks.

---

## 🔍 Features

- Preprocessing pipeline using OpenCV (grayscale conversion, thresholding, noise reduction, resizing).
- Model options:
  - Convolutional Neural Network (CNN)
  - CNN + BiLSTM sequence model for multi-character CAPTCHAs
- End-to-end training pipeline (`train.py`) using a synthetic CAPTCHA generator.
- Inference script (`solve.py`) for single/multi-image CAPTCHA solving.
- Compatibility with common formats: alphanumeric, distorted text, simple arithmetic.

---

## 🛠️ Installation

1. Clone the repo:
    ```bash
    git clone https://github.com/Shashankkusu/Captcha-solver.git
    cd Captcha-solver
    ```

2. Create and activate a virtual environment (optional but recommended):
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # Linux/macOS
    venv\Scripts\activate     # Windows
    ```

3. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

---

## 📁 Repository Structure

Captcha-solver/
├── data/ # Generated CAPTCHA datasets (train/test)
├── models/ # Trained model checkpoints
├── src/
│ ├── generator.py # CAPTCHA image generator
│ ├── preprocess.py # Image preprocessing utilities
│ ├── model.py # CNN / CNN-BiLSTM model definitions
│ ├── train.py # Training loop & evaluation
│ └── solve.py # Inference script
├── requirements.txt # Python dependencies
└── README.md

yaml
Copy
Edit

---

## 🎯 Usage

### Generate a dataset:
```bash
python src/generator.py --count 5000 --length 5
Train the model:
bash
Copy
Edit
python src/train.py \
  --data-dir data/ \
  --epochs 100 \
  --batch-size 64 \
  --model models/captcha_cnn_bilstm.pth
Solve a CAPTCHA:
bash
Copy
Edit
python src/solve.py \
  --model models/captcha_cnn_bilstm.pth \
  --image examples/captcha01.png
📊 Results
Model	Accuracy (per-character)	Notes
CNN baseline	~XX%	Single-character per slice
CNN + BiLSTM	~YY%	Sequence prediction

You can improve performance with better data augmentation, model tuning, or more training epochs.

🧩 Contributing
Fork this repository and clone it.

Create a new branch (git checkout -b feature/my-feature).

Commit your improvements (git commit -m "Add awesome feature").

Push to your fork (git push origin feature/my-feature).

Open a pull request — contributions are welcome!

🧭 License
This project is licensed under the MIT License – see the LICENSE file for details.

⚠️ Disclaimer
Intended for educational and research purposes only. Do not use to bypass CAPTCHA protections for malicious or unauthorized automation. Always comply with terms of service and applicable laws and regulations.

🤝 Acknowledgements
Inspired by repositories such as jameskokoska/CAPTCHA-Solver

Utilizes libraries: OpenCV, NumPy, PyTorch/TensorFlow, Pillow, optionally TensorFlow Addons
