# YOLOv8l Baseline — VisDrone

This repository provides a **reproducible baseline** for training the YOLOv8l model on the **VisDrone2019-DET** dataset.  
All code, paths, weights, and results are preserved exactly as generated.  
The dataset is **not redistributed**; instead, you can fetch it automatically via **KaggleHub**.  

> **Environment:** All experiments were run on **Google Colab Pro** with **High-RAM runtime** and an **NVIDIA A100 GPU**.

---

## 📂 Repository Structure
```
YOLOv8l/
├─ YOLOv8l Baseline.ipynb        # main Colab notebook
├─ runs/
│   └─ yolov8_training/
│       ├─ train/                # training outputs
│       │   ├─ results.png
│       │   ├─ confusion_matrix.png
│       │   ├─ confusion_matrix_normalized.png
│       │   ├─ results.csv
│       │   ├─ val_per_class_ap.csv
│       │   ├─ BoxF1_curve.png
│       │   ├─ BoxP_curve.png
│       │   ├─ BoxR_curve.png
│       │   ├─ BoxPR_curve.png
│       │   ├─ args.yaml
│       │   └─ weights/          # best.pt, last.pt, ONNX, TorchScript, etc. (via Git LFS)
│       └─ test_infer/           # inference results
├─ requirements.txt
├─ LICENSE
├─ CITATION.cff
├─ CODE_OF_CONDUCT.md
├─ CONTRIBUTING.md
├─ SECURITY.md
├─ CHANGELOG.md
├─ .gitignore
├─ .gitattributes
└─ .github/workflows/smoke.yml
```
---

## 📊 Dataset

We do not redistribute the dataset. Download it programmatically with KaggleHub:

```bash
pip install kagglehub
```

```python
import kagglehub
from pathlib import Path

path = kagglehub.dataset_download("banuprasadb/visdrone-dataset")
print("Path to dataset files:", path)


DATA_ROOT = Path(path) / "VisDrone"
print("DATA_ROOT:", DATA_ROOT)
```

On Kaggle, the dataset is available at:
/kaggle/input/visdrone-dataset/VisDrone_Dataset/
├─ VisDrone2019-DET-train/
├─ VisDrone2019-DET-val/
├─ VisDrone2019-DET-test-dev/
├─ VisDrone2019-DET-test-challenge/
└─ visdrone.yaml

```yaml
path: /kaggle/input/visdrone-dataset/VisDrone_Dataset
train: VisDrone2019-DET-train/images
val:   VisDrone2019-DET-val/images
test:  VisDrone2019-DET-test-dev/images
names: [pedestrian, people, bicycle, car, van, truck, tricycle, awning-tricycle, bus, motor]
```

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## ⚙️ Training Configuration

All hyperparameters are frozen in `args.yaml`.  
Key parameters:

- **Model**: `yolov8l.pt`  
- **Epochs**: 150  
- **Image size**: 640 × 640  
- **Batch size**: 16  
- **Workers**: 8  
- **Device**: GPU (A100, Colab Pro High-RAM)  
- **Framework**: Ultralytics YOLOv8 v8.3.5  
- **Torch**: 2.2+  


⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## 📈 Results

Located in `runs/yolov8_training/train/`:

- `results.png`: training curves  
- `confusion_matrix.png`, `confusion_matrix_normalized.png`  
- `BoxP_curve.png`, `BoxR_curve.png`, `BoxF1_curve.png`, `BoxPR_curve.png`  
- `results.csv`: per-epoch metrics  
- `val_per_class_ap.csv`: per-class AP values  
- `args.yaml`: training args  

Weights and exports (`best.pt`, `onnx`, `engine`, `torchscript`, etc.) are tracked via **Git LFS**.


⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## 🚀 Usage

**Clone and install**
```bash
git clone https://github.com/<your-username>/YOLOv8l.git
cd YOLOv8l
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
```

## Run the notebook

Open YOLOv8l Baseline.ipynb in Colab Pro (High-RAM, A100 GPU) or Jupyter.
Mount the dataset (via KaggleHub or manually) and run the cells.

## Inference
```bash
from ultralytics import YOLO
model = YOLO("runs/yolov8_training/train/weights/best.pt")
model.predict(source="path/to/images", imgsz=640, save=True)
```

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## 🧩 Reproducibility

- Notebook and outputs are preserved exactly.  
- Dataset is external via KaggleHub.  
- Weights and exports tracked with Git LFS.  
- CI workflow (`.github/workflows/smoke.yml`) validates environment and imports.  
- Training confirmed on **Colab Pro High-RAM A100 GPU runtime**.  

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## 📜 License

MIT License

Copyright (c) 2025 Abdul Rafay Mohd

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## 📚 Citation

If you use this repository or report results from it, please cite:
@software{YOLOv8l_Baseline_2025,
  author       = {Abdul Rafay Mohd},
  title        = {YOLOv8l Baseline — VisDrone},
  year         = {2025},
  publisher    = {GitHub},
  url          = {https://github.com/Mohd-Abdul-Rafay/YOLOv8l}
}

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## 🤝 Contributing

Contributions are welcome. See CONTRIBUTING.md￼.

⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻⸻

## 🔒 Security

See SECURITY.md￼ for vulnerability reporting.
---

✅ Copy everything above into GitHub’s web editor for `README.md` → Commit → Done.  

Do you also want me to hand you **ready-made boilerplate text** for `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, and `CHANGELOG.md` so the rest of your repo matches this quality?
