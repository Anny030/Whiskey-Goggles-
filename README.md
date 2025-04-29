
# Whisky Goggles - Whisky Bottle Identifier

## Overview
**Whisky Goggles** is a computer vision tool designed to identify whisky bottles by scanning their labels. It uses a custom-trained object detection and classification model to recognize bottle types, providing whisky enthusiasts and shoppers with an easy way to log and verify bottles in stores.

This project was developed for the **BAXATHON 2025 Challenge**.

---

## Features
- Detects and classifies whisky bottles from photos
- Handles real-world conditions like:
  - Angled photos
  - Partial labels
  - Low lighting
- Provides confidence scores for each prediction
- Easy integration via API

---

## Dataset
- A custom dataset of 500+ whisky bottles
- Manually annotated using Roboflow
- Trained using a `Detect and Classify` workflow

---

## Deployment Details
- **Workspace**: `baxathon`
- **Workflow ID**: `detect-and-classify-5`
- **API Endpoint (Serverless)**:  
  [`https://serverless.roboflow.com/infer/workflows/baxathon/detect-and-classify-5`](https://serverless.roboflow.com/infer/workflows/baxathon/detect-and-classify-5)

---

## Sample Image

This is a test image used during training and model validation:

![Sample Whisky Bottle](https://raw.githubusercontent.com/Anny030/Whiskey-Goggles-/main/35bc2bfe4757f6f2682bfd8bc39a3347(1).jpg)

You can use this to test the inference pipeline.

---

## Usage

### Python Inference Example

```python
from inference_sdk import InferenceHTTPClient

client = InferenceHTTPClient(
    api_url="https://detect.roboflow.com",
    api_key="SnUkOeOUzWovQoX3PIck"

result = client.run_workflow(
    workspace_name="baxathon",
    workflow_id="detect-and-classify-5",
    images={
        "image": "https://raw.githubusercontent.com/Anny030/Whiskey-Goggles-/main/35bc2bfe4757f6f2682bfd8bc39a3347(1).jpg"
    },
    use_cache=True
)

print(result)
