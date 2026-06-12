# 🧬 MultiModal Drug Response Transformer Project

A Multimodal Deep Learning Model for Predicting Drug Response using Drug Features and RNA Expression Data.

# 🚀 How to Run This Project Locally

## 1️⃣ Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/drug-response-transformer.git
cd drug-response-transformer
```

Replace `YOUR_USERNAME` with your GitHub username.

---

## 2️⃣ Create a Conda Environment (Recommended)

```bash
conda create -n drug_response python=3.9 -y
conda activate drug_response
```

If you don’t use Conda, you can create a virtual environment:

```bash
python -m venv venv
venv\Scripts\activate   # Windows
source venv/bin/activate  # Mac/Linux
```

---

## 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

If installation fails, install manually:

```bash
pip install torch torchvision torchaudio
pip install numpy pandas scikit-learn matplotlib tqdm fastapi uvicorn
```

---

## 4️⃣ Verify PyTorch Installation

```bash
python -c "import torch; print(torch.__version__)"
```

---

# 🧠 Train the Model

```bash
python -m src.train
```

This will:
- Load the dataset
- Train the multimodal model
- Save the trained model as `model.pt`

---

# 📊 Evaluate the Model

```bash
python -m src.evaluate
```

---

# 🔍 Interpret Attention

```bash
python -m src.interpret_attention
```

---

# 🚀 Run the API Locally (Deployment)

## Start the FastAPI Server

```bash
uvicorn deployment.app:app --reload
```

Server will start at:

```
http://127.0.0.1:8000
```

---

## Open Interactive API Documentation

Visit in your browser:

```
http://127.0.0.1:8000/docs
```

---

## Example Prediction Input

```json
{
  "drug": [0.1,0.2,0.3,0.4,0.5,0.6,0.7,0.8,0.9,1.0],
  "rna":  [1.0,0.9,0.8,0.7,0.6,0.5,0.4,0.3,0.2,0.1]
}
```

---

# 📂 Project Structure

```
DRUG-RESPONSE-TRANSFORMER/
│
├── data/                  
├── deployment/            
├── scripts/               
├── src/                   
│   ├── dataset.py
│   ├── drug_encoder.py
│   ├── rna_encoder.py
│   ├── multimodal_model.py
│   ├── train.py
│   ├── evaluate.py
│   └── interpret_attention.py
│
├── model.pt               
├── requirements.txt
└── README.md
```

---

# ⚠️ Common Issues

### ModuleNotFoundError: src

Run using:

```bash
python -m src.train
```

instead of:

```bash
python src/train.py
```

---

### CUDA Error (No GPU)

If running on CPU only:

```python
torch.load("model.pt", map_location="cpu")
```

---

# 🖥️ System Requirements

- Python 3.9+
- Conda (recommended)
- PyTorch
- Minimum 8GB RAM
- Optional: NVIDIA GPU for faster training
