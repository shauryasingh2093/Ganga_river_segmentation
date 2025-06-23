# 🛰️ Ganga River Shrinkage Detection using Semantic Segmentation

This project detects and quantifies the shrinkage of the Ganga River over the past decade using satellite imagery, NDWI (Normalized Difference Water Index), and semantic segmentation with DeepLabV3+ in PyTorch. The analysis focuses on three major cities: **Prayagraj**, **Varanasi**, and **Patna**, comparing data from 2014 and 2024.

---

## 📌 Overview

- **Satellite Datasets**: Landsat-8 (2014) and Sentinel-2 (2024)
- **Target Output**: Water body segmentation masks
- **Technique**: Semantic segmentation using DeepLabV3+
- **Frameworks Used**: PyTorch, Google Earth Engine, OpenCV, segmentation_models.pytorch

---

## 🧠 Model Description

- **Model**: DeepLabV3+ (Pretrained on ImageNet)
- **Backbone**: ResNet (configurable)
- **Loss Functions**: Dice Loss + Cross Entropy Loss
- **Metrics**: IoU (Intersection over Union), Accuracy
- **Data Format**: PNG or JPEG images of satellite views and binary water masks

---

## 🗂️ Folder Structure

📁 GangaRiverShrinkage/
├── Ganga_Images/ # NDWI images exported from GEE
├── imageData/ # Input satellite images
├── maskData/ # NDWI-based ground truth masks
├── model/ # Trained DeepLabV3+ model checkpoints
├── outputs/ # Predicted masks and visualization results
├── Untitled2.ipynb # Main notebook for training, testing, and inference
└── README.md # Project documentation


---

## 📥 Data Preparation

NDWI is computed using:
```python
NDWI = (Green - NIR) / (Green + NIR)
Landsat-8 Bands: Green (B3), NIR (B5)

Sentinel-2 Bands: Green (B3), NIR (B8)

Exported NDWI images from Google Earth Engine are used as input and binary masks.

🚀 Getting Started
1. Clone the Repository
bash
Copy code
git clone https://github.com/yourusername/GangaRiverShrinkage.git
cd GangaRiverShrinkage
2. Install Dependencies
bash
Copy code
pip install -r requirements.txt
💡 Additional requirements (if not in requirements.txt):

bash
Copy code
pip install segmentation-models-pytorch
pip install torch torchvision
pip install opencv-python
pip install matplotlib
3. Authenticate Google Earth Engine (Optional)
python
Copy code
import ee
ee.Authenticate()
ee.Initialize()
4. Run the Notebook
Launch Jupyter and execute all cells in Untitled2.ipynb:

bash
Copy code
jupyter notebook Untitled2.ipynb
📊 Results
Visual comparisons of water bodies between 2014 and 2024

IoU and Accuracy metrics for model performance

Quantified shrinkage area using mask comparisons

🔍 Sample Output
Year	Water Mask Example
2014	
2024	

✅ To-Do
 Segment water bodies using DeepLabV3+

 Visualize changes over time

 Automate GEE NDWI export in Python

 Integrate seasonal change analysis

 Extend to other river locations

🛠️ Tech Stack
Google Earth Engine – Satellite imagery and NDWI export

PyTorch – Deep learning framework

OpenCV / Matplotlib – Visualization and mask handling

Jupyter Notebook – Workflow orchestration

🙏 Acknowledgements
Google Earth Engine

Landsat & Sentinel Missions

PyTorch

segmentation_models.pytorch

📄 License
This project is licensed under the MIT License.


You can now paste this entire content as your `README.md` file in the root of your GitHub repository. Let me know if you also want:

- A matching `requirements.txt`
- Auto-run script (`train.py` / `inference.py`)
- Preview images or model performance graphs
