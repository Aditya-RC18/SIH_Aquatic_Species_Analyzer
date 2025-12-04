# 🐟 Fish-Sense

### **Automated Biomass Estimation & Early Disease Detection in Aquaculture**

Fish-Sense is a computer-vision–based system designed to assist fish farmers and researchers by automatically estimating fish biomass and detecting early signs of disease. Instead of depending on manual measurements or expert inspection, this project uses deep learning to analyze fish images and provide accurate, fast, and easy-to-understand results — all through a simple web interface.

---

## 📌 What This Project Does

When an image is uploaded, Fish-Sense performs **three major tasks**:

### **1️⃣ Fish Segmentation & Measurement**

* Uses **Mask R-CNN** to detect fish in the image.
* Generates a **segmentation mask**.
* Measures **length**, **height**, and related geometric parameters.
* These measurements are used for biomass estimation.

### **2️⃣ Fish Species Classification**

* A CNN identifies the **fish species**.
* Supports multiple aquaculture-relevant species.

### **3️⃣ Fish Health Analysis**

* Classifies fish as **Healthy** or **Unhealthy**.
* If unhealthy, the model detects:

  * **Bacterial infection type**
  * **Location of infection** on the fish body

All results appear visually and in a clean results table.

---

## 🧠 How the System Works

Below is the complete system workflow:

![Methodology](/Fig/Methodology_diagram.png)

### Simple Processing Steps:

1. **Upload an image** through the web app
2. The backend models analyze the fish:

   * Mask-RCNN → segmentation + measurements
   * CNN → species classification
   * CNN → health and disease detection
3. You receive:

   * A processed image
   * A results table summarizing biomass, species, and health

---

## 📝 Abstract (Simple Student-Friendly Version)

Aquaculture is growing quickly due to rising demand for seafood, but fish farms still struggle with disease outbreaks and inaccurate biomass measurements. These issues lead to lower productivity and financial losses. Fish-Sense provides a deep-learning–powered solution that helps farmers monitor fish health and estimate biomass automatically.

The system includes models for:

* Fish segmentation
* Species classification
* Healthy/unhealthy detection
* Body-part segmentation

To support model training, four custom datasets were created from real fish farm environments. The final models show strong accuracy and can support automated fish health monitoring, contributing to smarter and more sustainable aquaculture practices.

---

## 📦 Datasets & Pretrained Models

This project uses **four custom-built datasets** created specifically for aquaculture-based deep learning tasks:

* **Fish Segmentation Dataset**
* **Fish Species Classification Dataset**
* **Healthy vs Unhealthy Classification Dataset**
* **Fish Body-Part Segmentation Dataset**

Training notebooks (Google Colab files) are provided inside:

```
colab training - file/
```

Pretrained model weights should be placed inside:

```
trained_models/
```

---

## 🛠 Requirements

* Python 3.7+
* PyTorch
* OpenCV 4.8.0.74
* Django 3.2.8
* djangorestframework 3.12.4
* imutil 0.3.4
* imutils 0.5.4
* TensorFlow 2.13.0
* SciPy 1.11.1

---

## ⚙️ Installation Instructions

### **1️⃣ Create a Conda environment**

```bash
conda create --name your_env_name python
conda activate your_env_name
```

### **2️⃣ Install PyTorch**

**Windows (CPU only):**

```bash
conda install pytorch torchvision torchaudio cpuonly -c pytorch
```

For GPU/Linux, check official instructions:
[https://pytorch.org/get-started/locally/](https://pytorch.org/get-started/locally/)

### **3️⃣ Install OpenCV**

```bash
pip install opencv-python
```

### **4️⃣ Install Detectron2**

```bash
python -m pip install 'git+https://github.com/facebookresearch/detectron2.git'
```

### **5️⃣ Install all project dependencies**

```bash
pip install -r requirements.txt
```

---

## ▶️ Running the Project

Start the Django backend:

```bash
python manage.py runserver
```

Open the app at:

```
http://127.0.0.1:8000/
```

Upload an image → Click **Send**

Sample images are available in:

```
detection_labels/images/
```

---

## 🔍 Output Examples

Here’s how the system looks during use:

### **Web Interface**

![Demo UI](/Fig/Demo_prototype.jpg)

### **Final Results Display**

![Demo Results](/Fig/Demo_prototype2.jpg)

---

## 🎯 Final Notes

Fish-Sense demonstrates how AI can help make aquaculture smarter and more sustainable by:

* Reducing manual workload
* Supporting early disease detection
* Improving biomass tracking
* Helping farmers make quick, informed decisions

This project is perfect for:

* Students
* Researchers
* Developers
* Aquaculture professionals

Feel free to modify, expand, or build upon the system!

---
