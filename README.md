The project pioneers an advanced insect detection system leveraging the YOLOv8 model to revolutionize pest management in agriculture.
By integrating multi-scale dense YOLO (MD-YOLO) technology, it ensures unparalleled accuracy in detecting even the smallest targets amidst complex backgrounds.
A meticulously curated dataset, crafted using the bound boxing technique, underpins the project's robust detection capabilities.
Grounded in extensive research and enriched by a plethora of scholarly insights, the project delves deep into pest behavior and detection mechanisms.
This innovative system is poised to dramatically reduce crop damage, fostering more sustainable and productive agricultural practices.
# Agricultural Insect Detection System

An enterprise-grade computer vision solution leveraging the YOLO framework and multi-scale dense YOLO (MD-YOLO) technology to revolutionize pest management in precision agriculture. Engineered to isolate and detect exceptionally small target pests amidst complex, dynamic field backgrounds, this system mitigates crop damage and promotes sustainable, high-yield farming practices.

---

## **Features**

* **MD-YOLO Architecture:** Integrates multi-scale dense feature extraction layers optimized for capturing ultra-small pests with high localization precision.
* **YOLOv8 Backbone:** Employs cutting-edge object detection algorithms to balance rapid inference speeds with state-of-the-art accuracy.
* **Complex Background Robustness:** Filters out visual noise from foliage, shadows, and changing lighting conditions to reduce false positives.
* **Research-Backed Design:** Built on extensive behavioral research and spatial distribution patterns of primary agricultural pests.

---

## **Tech Stack**

* **Language:** Python 3.10+
* **Core Framework:** Ultralytics YOLOv8, PyTorch
* **Data Annotation:** Bounding Box Tagging (`LabelImg`, `Roboflow`)
* **Core Libraries:** OpenCV, NumPy, Pandas

---

## **Project Structure**

```text
insect-detection-yolov8/
│
├── dataset/
│   ├── images/
│   └── labels/
│
├── weights/
│   └── md_yolov8_best.pt
│
├── data.yaml
├── train.py
├── detect.py
├── requirements.txt
└── README.md

```

---

## **Installation & Setup**

**1. Clone the Repository**

```bash
git clone https://github.com/your-username/pest-detection-yolov8.git
cd pest-detection-yolov8

```

**2. Create a Virtual Environment**

```bash
python -m venv venv
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

```

**3. Install Dependencies**

```bash
pip install -r requirements.txt

```

*(Alternatively, install core packages manually: `pip install ultralytics opencv-python numpy`)*

---

## **Usage**

Run the training script to fine-tune the model on your custom dataset:

```bash
python train.py

```

Run inference on sample field images or a live video feed:

```bash
python detect.py --weights weights/md_yolov8_best.pt --source data/samples/

```

* Press the **`q`** key on your keyboard to exit the application window during live detection.

---

## **Code Snippet (`train.py`)**

```python
from ultralytics import YOLO

# Load a pre-trained YOLOv8 model for custom training
model = YOLO("yolov8n.pt")

# Train the model on the agricultural insect dataset
results = model.train(
    data="data.yaml", 
    epochs=50, 
    imgsz=640, 
    batch=16, 
    name="insect_detector"
)

```

---
