<!-- PROJECT SUMMARY -->
<p align="center">

<h2 align="center">Awesome YOLOv8 Models</h2>
<h4 align="center">Easy-to-use finetuned YOLOv8 models</h4>

<p align="center">
    <strong>
        <a href="https://huggingface.co/models?other=awesome-yolov8-models">Demo</a>
        •
        <a href="https://github.com/keremberke/awesome-yolov8-models/">Github</a>
    </strong>
</p>

<p align="center">
    <img width="400px" src="https://user-images.githubusercontent.com/34196005/215836968-fb54e066-a524-4caf-b469-92bbaa96f921.gif" align="center" alt="Satellighte" />
<!-- TABLE OF CONTENTS -->
<details>
    <summary>
        <strong>
            TABLE OF CONTENTS
        </strong>
    </summary>
    <ol>
        <li>
            <a href="#about-the-project">About the Project</a>
        </li>
        <li>
            <a href="#installation">Installation</a>
        </li>
        <li><a href="#usage">Usage</a></li>
        <li><a href="#classification-models">Classification Models</a></li>
        <li><a href="#detection-models">Detection Models</a></li>
        <li><a href="#segmentation-models">Segmentation Models</a></li>
        <li><a href="#contributing">Contributing</a></li>
        <li><a href="#license">License</a></li>
    </ol>
</details>

<!-- ABOUT THE PROJECT -->
## About the Project

This is a collection of YOLOv8 models finetuned for classification/detection/segmentation tasks on datasets from various domains as Medicine/Insurance/Sports/Gaming.

> **Ultralytics YOLOv8**, developed by Ultralytics, is a cutting-edge, state-of-the-art (SOTA) model that builds upon the success of previous YOLO versions and introduces new features and improvements to further boost performance and flexibility. YOLOv8 is designed to be fast, accurate, and easy to use, making it an excellent choice for a wide range of object detection, image segmentation and image classification tasks.
>
> _Source: [github](https://github.com/ultralytics/ultralytics)

<!-- INSTALLATION -->
## Installation

To use listed models, install ultralyticsplus:

```bash
pip install ultralyticsplus
```

<!-- USAGE -->
## Usage

```python
from ultralyticsplus import YOLO, render_result

# load model
model = YOLO(DESIRED_MODEL_ID)
    
# set image
image = 'image.png'
    
# perform inference
results = model(image)

# parse results
result = results[0]
boxes = result.boxes.xyxy # x1, y1, x2, y2
scores = result.boxes.conf
categories = result.boxes.cls
scores = result.probs # for classification models
masks = result.masks # for segmentation models
    
# show results on image
render = render_result(model=model, image=image, result=result)
render.show()
```

<!-- CLASSIFICATION MODELS -->
## Classification Models

<img width="600px" src="https://user-images.githubusercontent.com/34196005/215838213-f845f8c6-2fb7-48ac-8f9a-48a39d37bc0e.png" align="center" />

| top1 acc. | top5 acc. | model type | model id |  dataset page |
|---        |---        |---         |---       |---            |
| 0.678 | 1.000 | yolov5n-cls | [keremberke/yolov8n-shoe-classification](https://huggingface.co/keremberke/yolov8n-shoe-classification) | [dataset](https://huggingface.co/datasets/keremberke/shoe-classification) |
| 0.678 | 1.000 | yolov5n-cls | [keremberke/yolov8n-shoe-classification](https://huggingface.co/keremberke/yolov8n-shoe-classification) | [dataset](https://huggingface.co/datasets/keremberke/shoe-classification) |
| 0.678 | 1.000 | yolov5n-cls | [keremberke/yolov8n-shoe-classification](https://huggingface.co/keremberke/yolov8n-shoe-classification) | [dataset](https://huggingface.co/datasets/keremberke/shoe-classification) |

<!-- DETECTION MODELS -->
## Detection Models

<img width="600px" src="https://user-images.githubusercontent.com/34196005/215834577-0984aaf4-3909-426d-b3d6-d3270328f312.png" align="center" />

| box mAP@0.5 | model type | model id |  dataset page |
|---                 |---         |---       |---            |
| 0.959 | yolov5n | [keremberke/yolov5n-valorant](https://huggingface.co/keremberke/yolov5n-valorant) | [dataset](https://huggingface.co/datasets/keremberke/valorant-object-detection) |
| 0.982 | yolov5s | [keremberke/yolov5s-valorant](https://huggingface.co/keremberke/yolov5s-valorant) | [dataset](https://huggingface.co/datasets/keremberke/valorant-object-detection) |
| 0.990 | yolov5m | [keremberke/yolov5m-valorant](https://huggingface.co/keremberke/yolov5m-valorant) | [dataset](https://huggingface.co/datasets/keremberke/valorant-object-detection) |

<!-- SEGMENTATION MODELS -->
## Segmentation Models

<img width="600px" src="https://user-images.githubusercontent.com/34196005/215839699-56772272-fd81-4e34-afe1-2adef72616ca.png" align="center" />

| mask mAP@0.5 | model type | model id |  dataset page |
|---            |---         |---         |---            |
| 0.517 | yolov5n-seg | [keremberke/yolov8n-pcb-defect-segmentation](https://huggingface.co/keremberke/yolov8n-pcb-defect-segmentation) | [dataset](https://huggingface.co/datasets/keremberke/pcb-defect-segmentation) |
| 0.517 | yolov5n-seg | [keremberke/yolov8n-pcb-defect-segmentation](https://huggingface.co/keremberke/yolov8n-pcb-defect-segmentation) | [dataset](https://huggingface.co/datasets/keremberke/pcb-defect-segmentation) |
| 0.517 | yolov5n-seg | [keremberke/yolov8n-pcb-defect-segmentation](https://huggingface.co/keremberke/yolov8n-pcb-defect-segmentation) | [dataset](https://huggingface.co/datasets/keremberke/pcb-defect-segmentation) |

<!-- CONTRIBUTING -->
## Contributing

To contribute to `Awesome-YOLOv8-Models`, follow these steps:

1. Train a YOLOv8 model with ultralytics package | [tutorial](https://github.com/ultralytics/ultralytics/blob/main/examples/tutorial.ipynb)
2. Push your model to hub with ultralyticsplus package | [package readme](https://github.com/fcakyon/ultralyticsplus#push-to--hub)
3. Open a PR or Discussion post in this repo with your hub id.

<!-- LICENSE -->
## License

This project is licensed under `MIT` license. See [`LICENSE`](LICENSE) for more information.

![-----------------------------------------------------](https://raw.githubusercontent.com/canturan10/readme-template/master/src/colored_4b.png)

Give a ⭐️ if this project helped you!
