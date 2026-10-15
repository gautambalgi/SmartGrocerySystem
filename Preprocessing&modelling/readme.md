# Dataset Exploration and YOLO Training

The [notebook](preprocessing%26modelling.ipynb) covers dataset inspection, bounding-box visualization, YOLO training, validation, and example predictions.

## Prepare the data

1. Download the [original dataset archive](https://drive.google.com/file/d/1HfQR301KV02c1FTm3zIAtiodv0-DgLak/view?usp=sharing), subject to its sharing permissions.
2. Open the notebook in Colab or Jupyter.
3. Update `zip_path`, `extract_path`, `yaml_path`, `dataset_path`, sample-image paths, and training/output paths to match your environment. The notebook mixes several original `/content` directory names; they must resolve to the same intended dataset.
4. Check `data.yaml`, class names, and `train`/`valid`/`test` image and label directories before training.

Dependencies used by the notebook include:

```bash
python -m pip install ultralytics opencv-python matplotlib numpy seaborn pillow pyyaml jupyterlab
```

## Workflow

- Count images and annotations and compare class distributions across splits.
- Plot sample bounding boxes, box-center heatmaps, and image dimensions.
- Check for corrupt images and missing or empty label files. Point `validate_dataset` at the actual image and label directories; its example arguments currently point at the dataset root.
- Fine-tune `yolov8n.pt`. The executable call uses `epochs=25`, `imgsz=640`, and `batch=16`; an earlier prose description refers to a different, two-epoch run.
- Load the resulting checkpoint, call `model.val()`, and generate annotated predictions.

The final chart uses manually entered scores and reuses validation metrics despite a “Test Set” heading. It is not proof of a separate held-out test evaluation. Choose the intended evaluation split explicitly when reproducing results.

The dataset is external. The application checkpoint is already included at [`../FinalApp/best.pt`](../FinalApp/best.pt), so retraining is not required to try the desktop app.

See the [main README](../README.md) for the application workflow, recorded metrics, and project limitations.
