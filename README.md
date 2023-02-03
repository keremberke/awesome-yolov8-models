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
| 0.678 | 1.000 | yolov8n-cls | [keremberke/yolov8n-shoe-classification](https://huggingface.co/keremberke/yolov8n-shoe-classification) | [dataset](https://huggingface.co/datasets/keremberke/shoe-classification) |
| 0.687 | 1.000 | yolov8s-cls | [keremberke/yolov8s-shoe-classification](https://huggingface.co/keremberke/yolov8s-shoe-classification) | [dataset](https://huggingface.co/datasets/keremberke/shoe-classification) |
| 0.795 | 1.000 | yolov8m-cls | [keremberke/yolov8m-shoe-classification](https://huggingface.co/keremberke/yolov8m-shoe-classification) | [dataset](https://huggingface.co/datasets/keremberke/shoe-classification) |

<img width="600px" src="https://user-images.githubusercontent.com/89259176/215867937-03134da0-afd6-4dac-b5fd-6d68a58004d4.png" align="center" />

| top1 acc. | top5 acc. | model type | model id |  dataset page |
|---        |---        |---         |---       |---            |
| 0.943 | 1.000 | yolov8n-cls | [keremberke/yolov8n-chest-xray-classification](https://huggingface.co/keremberke/yolov8n-chest-xray-classification) | [dataset](https://huggingface.co/datasets/keremberke/chest-xray-classification) |
| 0.942 | 1.000 | yolov8s-cls | [keremberke/yolov8s-chest-xray-classification](https://huggingface.co/keremberke/yolov8s-chest-xray-classification) | [dataset](https://huggingface.co/datasets/keremberke/chest-xray-classification) |
| 0.955 | 1.000 | yolov8m-cls | [keremberke/yolov8m-chest-xray-classification](https://huggingface.co/keremberke/yolov8m-chest-xray-classification) | [dataset](https://huggingface.co/datasets/keremberke/chest-xray-classification) |


<!-- DETECTION MODELS -->
## Detection Models

<img width="600px" src="https://user-images.githubusercontent.com/34196005/215834577-0984aaf4-3909-426d-b3d6-d3270328f312.png" align="center" />

| box mAP@0.5 | model type | model id |  dataset page |
|---                 |---         |---       |---            |
| 0.937 | yolov8n-det | [keremberke/yolov8n-valorant-detection](https://huggingface.co/keremberke/yolov8n-valorant-detection) | [dataset](https://huggingface.co/datasets/keremberke/valorant-object-detection) |
| 0.971 | yolov8s-det | [keremberke/yolov8s-valorant-detection](https://huggingface.co/keremberke/yolov8s-valorant-detection) | [dataset](https://huggingface.co/datasets/keremberke/valorant-object-detection) |
| 0.965 | yolov8m-det | [keremberke/yolov8m-valorant-detection](https://huggingface.co/keremberke/yolov8m-valorant-detection) | [dataset](https://huggingface.co/datasets/keremberke/valorant-object-detection) |

<img width="600px" src="https://user-images.githubusercontent.com/89259176/216049393-a86cc5e6-c9aa-4186-9f13-6ac0a31b8681.png" align="center" />

| box mAP@0.5 | model type | model id |  dataset page |
|---                 |---         |---       |---            |
| 0.838 | yolov8n-det | [keremberke/yolov8n-forklift-detection](https://huggingface.co/keremberke/yolov8n-forklift-detection) | [dataset](https://huggingface.co/datasets/keremberke/forklift-object-detection) |
| 0.851 | yolov8s-det | [keremberke/yolov8s-forklift-detection](https://huggingface.co/keremberke/yolov8s-forklift-detection) | [dataset](https://huggingface.co/datasets/keremberke/forklift-object-detection) |
| 0.846 | yolov8m-det | [keremberke/yolov8m-forklift-detection](https://huggingface.co/keremberke/yolov8m-forklift-detection) | [dataset](https://huggingface.co/datasets/keremberke/forklift-object-detection) |

<img width="600px" src="https://user-images.githubusercontent.com/89259176/216603426-45a0b43a-08dd-4edf-98ab-3d5d8e062109.png" align="center" />

| box mAP@0.5 | model type | model id |  dataset page |
|---                 |---         |---       |---            |
| 0.844 | yolov8n-det | [keremberke/yolov8n-csgo-player-detection](https://huggingface.co/keremberke/yolov8n-csgo-player-detection) | [dataset](https://huggingface.co/datasets/keremberke/csgo-object-detection) |
| 0.886 | yolov8s-det | [keremberke/yolov8s-csgo-player-detection](https://huggingface.co/keremberke/yolov8s-csgo-player-detection) | [dataset](https://huggingface.co/datasets/keremberke/csgo-object-detection) |
| 0.892 | yolov8m-det | [keremberke/yolov8m-csgo-player-detection](https://huggingface.co/keremberke/yolov8m-csgo-player-detection) | [dataset](https://huggingface.co/datasets/keremberke/csgo-object-detection) |

<img width="600px" src="https://user-images.githubusercontent.com/89259176/216605070-d3b2721f-07bc-465b-9650-3e2e3d2e533b.png" align="center" />

| box mAP@0.5 | model type | model id |  dataset page |
|---                 |---         |---       |---            |
| 0.893 | yolov8n-det | [keremberke/keremberke/yolov8n-blood-cell-detection](https://huggingface.co/keremberke/keremberke/yolov8n-blood-cell-detection) | [dataset](https://huggingface.co/datasets/keremberke/blood-cell-object-detection) |
| 0.917 | yolov8s-det | [keremberke/keremberke/yolov8s-blood-cell-detection](https://huggingface.co/keremberke/keremberke/yolov8s-blood-cell-detection) | [dataset](https://huggingface.co/datasets/keremberke/blood-cell-object-detection) |
| 0.927 | yolov8m-det | [keremberke/keremberke/yolov8m-blood-cell-detection](https://huggingface.co/keremberke/keremberke/yolov8m-blood-cell-detection) | [dataset](https://huggingface.co/datasets/keremberke/blood-cell-object-detection) |


<!-- SEGMENTATION MODELS -->
## Segmentation Models

<img width="600px" src="https://user-images.githubusercontent.com/34196005/215839699-56772272-fd81-4e34-afe1-2adef72616ca.png" align="center" />

| mask mAP@0.5 | model type | model id |  dataset page |
|---            |---         |---         |---            |
| 0.517 | yolov8n-seg | [keremberke/yolov8n-pcb-defect-segmentation](https://huggingface.co/keremberke/yolov8n-pcb-defect-segmentation) | [dataset](https://huggingface.co/datasets/keremberke/pcb-defect-segmentation) |
| 0.491 | yolov8s-seg | [keremberke/yolov8s-pcb-defect-segmentation](https://huggingface.co/keremberke/yolov8s-pcb-defect-segmentation) | [dataset](https://huggingface.co/datasets/keremberke/pcb-defect-segmentation) |
| 0.557 | yolov8m-seg | [keremberke/yolov8m-pcb-defect-segmentation](https://huggingface.co/keremberke/yolov8m-pcb-defect-segmentation) | [dataset](https://huggingface.co/datasets/keremberke/pcb-defect-segmentation) |

<img width="600px" src="https://user-images.githubusercontent.com/89259176/216034949-80535a86-549f-45e5-af16-93f7a3a3c363.png" align="center" />

| mask mAP@0.5 | model type | model id |  dataset page |
|---            |---         |---         |---            |
| 0.628 | yolov8n-seg | [keremberke/yolov8n-building-segmentation](https://huggingface.co/keremberke/yolov8n-building-segmentation) | [dataset](https://huggingface.co/datasets/keremberke/satellite-building-segmentation) |
| 0.651 | yolov8s-seg | [keremberke/yolov8s-building-segmentation](https://huggingface.co/keremberke/yolov8s-building-segmentation) | [dataset](https://huggingface.co/datasets/keremberke/satellite-building-segmentation) |
| 0.613 | yolov8m-seg | [keremberke/yolov8m-building-segmentation](https://huggingface.co/keremberke/yolov8m-building-segmentation) | [dataset](https://huggingface.co/datasets/keremberke/satellite-building-segmentation) |

<img width="600px" src="https://user-images.githubusercontent.com/89259176/216039366-26af6a39-a080-46cf-8b7a-6622a022e421.png" align="center" />

| mask mAP@0.5 | model type | model id |  dataset page |
|---            |---         |---         |---            |
| 0.995 | yolov8n-seg | [keremberke/yolov8n-pothole-segmentation](https://huggingface.co/keremberke/yolov8n-pothole-segmentation) | [dataset](https://huggingface.co/datasets/keremberke/pothole-segmentation) |
| 0.928 | yolov8s-seg | [keremberke/yolov8s-pothole-segmentation](https://huggingface.co/keremberke/yolov8s-pothole-segmentation) | [dataset](https://huggingface.co/datasets/keremberke/pothole-segmentation) |
| 0.895 | yolov8m-seg | [keremberke/yolov8m-pothole-segmentation](https://huggingface.co/keremberke/yolov8m-pothole-segmentation) | [dataset](https://huggingface.co/datasets/keremberke/pothole-segmentation) |


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
