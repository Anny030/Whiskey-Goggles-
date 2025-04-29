# Whisky Goggles - Whisky Bottle Identifier

## Overview
Whisky Goggles is a computer vision tool that scans whisky bottle labels and identifies them using a custom-trained model on Roboflow. This is designed to help users recognize whisky types and log pricing while shopping.

## Features
- Single bottle detection and classification
- Trained on custom annotated whisky label images
- Works in real-world conditions (angle, lighting, partial views)

## Model Workflow
This project uses a "Detect and Classify" workflow deployed on Roboflow.

- **Workspace**: baxathon
- **Workflow ID**: detect-and-classify-5
- **API Endpoint**: `https://detect.roboflow.com`

## Inference (Python Example)
```python
from inference_sdk import InferenceHTTPClient

client = InferenceHTTPClient(
    api_url="https://detect.roboflow.com",
    api_key="SnUkOeOUzWovQoX3PIck "
)

result = client.run_workflow(
    workspace_name="baxathon",
    workflow_id="detect-and-classify-5",
    images={
        "image": "https://raw.githubusercontent.com/Anny030/Whiskey-Goggles-/main/35bc2bfe4757f6f2682bfd8bc39a3347(1).jpg"
    },
    use_cache=True
)

print(result)

##How to Use##

1. Clone this repository.
2. Replace YOUR_API_KEY with your actual Roboflow API key.
3. Run the Python script to test with the provided sample image or use your own.



Deliverables

1.Trained and deployed model on Roboflow
2.Sample whisky image for testing
3.API integration code
4.This README file with all usage details


License
This project is for educational/demo purposes only.

Credits
Developed by [Balogun Aneefat] for the BAXATHON 2025 competition.

