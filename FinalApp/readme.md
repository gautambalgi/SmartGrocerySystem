# Webcam Application

This directory contains the Smart Grocery System desktop interface and its trained weights.

| File | Purpose |
|---|---|
| `app.py` | Tkinter GUI, webcam capture, YOLO detection, rule-based recommendations, and in-memory cart |
| `best.pt` | Bundled detector weights |

## Run locally

Install Python with Tkinter and these packages:

```bash
python -m pip install ultralytics opencv-python pillow
```

In `app.py`, replace the original absolute model path in the `__main__` block with:

```python
app = YOLOCameraApp(root, model_path="best.pt")
```

From this directory, run:

```bash
python app.py
```

Click **Start** for live detections, **Add to Cart** to store unique detected names, **Clear Cart** to reset them, and **Stop** to release the camera. The app uses camera index `0` and a detection confidence threshold of `0.3`.

Recommendations come from `recommendation_buckets`, a fixed mapping of product names. They exclude products already detected in the current frame. The cart does not store quantities, prices, or data between sessions.

See the [main README](../README.md) for full setup instructions, troubleshooting, training details, and limitations.
