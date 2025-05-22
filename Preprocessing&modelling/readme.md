# Object Detection and Recommendation for Retail

This folder contains a Jupyter Notebook (`.ipynb`) that walks through the **data preprocessing**, **YOLO model training**, and **evaluation** process for an object detection task.

---

## 📁 Files Included

- `preprocessing&modelling.ipynb` – Main notebook that performs:
  - Dataset preparation
  - Annotation formatting (done earlier in LabelStudio)
  - YOLO-compatible preprocessing
  - Training a YOLO model
  - Evaluating performance with metrics and visualizations

---

## 📦 Dataset

📥 **Download the dataset from the following Google Drive link:**

**[Download Dataset](https://drive.google.com/file/d/1HfQR301KV02c1FTm3zIAtiodv0-DgLak/view?usp=sharing)**

### Instructions:
1. Click the link and download the ZIP or folder.
2. Extract the dataset.
3. Place the dataset in the **same directory** as the Jupyter notebook.
4. Update the file path inside the notebook if the extracted folder has a different name.

---

## 🛠 Requirements

Install the required Python libraries before running the notebook:

```bash
pip install ultralytics opencv-python matplotlib pandas

