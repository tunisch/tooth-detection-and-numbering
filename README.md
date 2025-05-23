<div align="center">
  <a href="https://ultralytics.com/yolo" target="_blank">
    <img width="1024" src="https://raw.githubusercontent.com/ultralytics/assets/main/yolov5/v70/splash.png">
  </a>

<div>
    <a href="#"><img src="https://img.shields.io/github/stars/tunisch/tooth-detection-and-numbering?style=social" alt="GitHub Stars"></a>
  </div>
  <br>

**Tooth Detection and Numbering from Panoramic Radiography Using Artificial Neural Networks** 🚀  
This repository contains the source code and resources for detecting and numbering teeth from panoramic radiography images. Developed as a graduate project at **T.C. Maltepe University**.

</div>
<br>


## 📚 Documentation

See See below for detailed information on setup, training, testing, and usage. See below for quickstart examples.

<details open>
<summary>Install</summary>

Clone the repository and install dependencies in a [**Python>=3.8.0**](https://www.python.org/) environment. Ensure you have [**PyTorch>=1.8**](https://pytorch.org/get-started/locally/) installed.

```bash
# Clone the YOLOv5 repository
git clone https://github.com/tunisch/tooth-detection-and-numbering

# Navigate to the cloned directory
cd yolov5

# Install required packages
pip install -r requirements.txt
```

</details>

<details open>
<summary>Inference with PyTorch Hub</summary>

Use YOLOv5 via [PyTorch Hub](https://docs.ultralytics.com/yolov5/tutorials/pytorch_hub_model_loading/) for inference. [Models](https://github.com/ultralytics/yolov5/tree/master/models) are automatically downloaded from the latest YOLOv5 [release](https://github.com/ultralytics/yolov5/releases).

```python
import torch

# Load the trained model for tooth detection and numbering
model = torch.hub.load("ultralytics/yolov5", "custom", path="path/to/your_trained_model.pt")  # Replace with your trained model path

# Define the input image source (URL, local file, PIL image, OpenCV frame, numpy array, or list)
img = "path/to/your/test_image.jpg"  # Replace with the path to your test image

# Perform inference (handles batching, resizing, normalization automatically)
results = model(img)

# Process the results (options: .print(), .show(), .save(), .crop(), .pandas())
results.print()  # Print results to console
results.show()  # Display results in a window
results.save()  # Save results to runs/detect/exp
```

</details>

<details>
<summary>Inference with detect.py</summary>

The `detect.py` script runs inference on various sources. It automatically downloads [models](https://github.com/ultralytics/yolov5/tree/master/models) from the latest YOLOv5 [release](https://github.com/ultralytics/yolov5/releases) and saves the results to the `runs/detect` directory.

```bash

# Run inference on an image or directory
python detect.py --weights best_model.pt --source data/test_images/

# Run inference on a text file listing image paths
python detect.py --weights yolov5s.pt --source list.txt

</details>

<details>
<summary>Training</summary>

The commands below demonstrate how to reproduce YOLOv5 [COCO dataset](https://docs.ultralytics.com/datasets/detect/coco/) results.
Both [models](https://github.com/ultralytics/yolov5/tree/master/models)
and [datasets](https://github.com/ultralytics/yolov5/tree/master/data) are downloaded automatically from the latest YOLOv5 [release](https://github.com/ultralytics/yolov5/releases).
Training times for YOLOv5n/s/m/l/x are approximately 1/2/4/6/8 days on a single [NVIDIA V100 GPU](https://www.nvidia.com/en-us/data-center/v100/).
Using [Multi-GPU training](https://docs.ultralytics.com/yolov5/tutorials/multi_gpu_training/) can significantly reduce training time.
Use the largest `--batch-size` your hardware allows, or use `--batch-size -1` for YOLOv5 [AutoBatch](https://github.com/ultralytics/yolov5/pull/5092).
The batch sizes shown below are for V100-16GB GPUs.


# Train the model on your dataset
python train.py --data data/dataset.yaml --epochs 100 --weights '' --cfg yolov5s.pt --batch-size 16

# Train YOLOv5n on COCO for 300 epochs
python train.py --data coco.yaml --epochs 300 --weights '' --cfg yolov5n.yaml --batch-size 128

# Train YOLOv5s on COCO for 300 epochs
python train.py --data coco.yaml --epochs 300 --weights '' --cfg yolov5s.yaml --batch-size 64

# Train YOLOv5m on COCO for 300 epochs
python train.py --data coco.yaml --epochs 300 --weights '' --cfg yolov5m.yaml --batch-size 40

# Train YOLOv5l on COCO for 300 epochs
python train.py --data coco.yaml --epochs 300 --weights '' --cfg yolov5l.yaml --batch-size 24

# Train YOLOv5x on COCO for 300 epochs
python train.py --data coco.yaml --epochs 300 --weights '' --cfg yolov5x.yaml --batch-size 16
```

<img width="800" src="results_combined.png" alt="YOLOv5 Training Results">

</details>

## 🧩 Integrations

Our key integrations with leading AI platforms extend the functionality of Ultralytics' offerings, enhancing tasks like dataset labeling, training, visualization, and model management.

<a href="https://docs.ultralytics.com/integrations/" target="_blank">
    <img width="100%" src="Integrations.png" alt="Ultralytics active learning integrations">
</a>
<br>
<div align="center" style="display: flex; justify-content: center; align-items: center; gap: 20px;">
  <a href="https://www.makesense.ai/">
    <img src="makesensei_ai.png" width="15%" alt="Makesense.ai"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="15%" style="margin-right: 20px; alt="space">
  <img src="https://github.com/ultralytics/assets/raw/main/partners/logo-wb.png" width="10%" alt="Weights & Biases logo">
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="15%" alt="space">
  <a href="https://www.tensorflow.org/tensorboard?hl=tr">
    <img src="TensorBoard.png" width="15%" alt="TensorBoard logo"></a>
</div>

|                                                       Make Sense AI 🌟                                                        |                                                          Weights & Biases                                                           |                                                                              TensorBoard                                                                              
| :-----------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------: | 
| Streamline YOLO workflows: Label, train, and deploy effortlessly with [Make Sense AI](https://www.makesense.ai/). Try now! | Track experiments, hyperparameters, and results with [Weights & Biases](https://docs.ultralytics.com/integrations/weights-biases/). | Free forever, [TensorBoard](https://www.tensorflow.org/tensorboard?hl=tr) lets you save YOLO models, resume training, and interactively visualize predictions. 


## 🤔 Why YOLOv5?

YOLOv5 is designed for simplicity and ease of use. We prioritize real-world performance and accessibility.

<p align="left"><img width="800" src="https://user-images.githubusercontent.com/26833433/155040763-93c22a27-347c-4e3c-847a-8094621d3f4e.png" alt="YOLOv5 Performance Chart"></p>
<details>
  <summary>YOLOv5-P5 640 Figure</summary>

<p align="left"><img width="800" src="https://user-images.githubusercontent.com/26833433/155040757-ce0934a3-06a6-43dc-a979-2edbbd69ea0e.png" alt="YOLOv5 P5 640 Performance Chart"></p>
</details>
<details>
  <summary>Figure Notes</summary>

- **COCO AP val** denotes the [mean Average Precision (mAP)](https://www.ultralytics.com/glossary/mean-average-precision-map) at [Intersection over Union (IoU)](https://www.ultralytics.com/glossary/intersection-over-union-iou) thresholds from 0.5 to 0.95, measured on the 5,000-image [COCO val2017 dataset](https://docs.ultralytics.com/datasets/detect/coco/) across various inference sizes (256 to 1536 pixels).
- **GPU Speed** measures the average inference time per image on the [COCO val2017 dataset](https://docs.ultralytics.com/datasets/detect/coco/) using an [AWS p3.2xlarge V100 instance](https://aws.amazon.com/ec2/instance-types/p4/) with a batch size of 32.
- **EfficientDet** data is sourced from the [google/automl repository](https://github.com/google/automl) at batch size 8.
- **Reproduce** these results using the command: `python val.py --task study --data coco.yaml --iou 0.7 --weights yolov5n6.pt yolov5s6.pt yolov5m6.pt yolov5l6.pt yolov5x6.pt`

</details>

### Pretrained Checkpoints for Dental Applications

This table highlights performance metrics for YOLOv5 models trained and fine-tuned on panoramic radiography datasets for tooth detection and numbering.


| Model                                                                                                                                                                    | Size<br><sup>(pixels) | mAP<sup>val<br>50-95 | Speed<br><sup>CPU b1<br>(ms) | Speed<br><sup>V100 b1<br>(ms) | Params<br><sup>(M) | FLOPs<br><sup>@640 (B) |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|-----------------------|-------------------------------|-------------------------------|--------------------|-------------------------|
| [YOLOv5n](https://github.com/tunisch/tooth-detection-and-numbering/releases/download/v1.0/yolov5n.pt)                                                                    | 640                    | 32.0                  | **50**                        | **8.0**                       | 1.9                | 4.5                     |
| [YOLOv5s](https://github.com/tunisch/tooth-detection-and-numbering/releases/download/v1.0/yolov5s.pt)                                                                    | 640                    | 40.5                  | 100                           | 8.5                           | 7.2                | 16.5                    |
| [YOLOv5m](https://github.com/tunisch/tooth-detection-and-numbering/releases/download/v1.0/yolov5m.pt)                                                                    | 640                    | 48.0                  | 230                           | 10.5                          | 21.2               | 49.0                    |
| [YOLOv5l](https://github.com/tunisch/tooth-detection-and-numbering/releases/download/v1.0/yolov5l.pt)                                                                    | 640                    | 52.5                  | 450                           | 12.0                          | 46.5               | 109.1                   |
| [YOLOv5x](https://github.com/tunisch/tooth-detection-and-numbering/releases/download/v1.0/yolov5x.pt)                                                                    | 640                    | 54.0                  | 800                           | 15.0                          | 86.7               | 205.7                   |

<details>
  <summary>Table Notes</summary>

- **Dataset:** All models were fine-tuned using a custom panoramic radiography dataset annotated for tooth detection and numbering.
- **Reproducibility:** Use the provided pretrained weights to reproduce results or fine-tune further using your dataset and the following command:<br>python train.py --data data/dental.yaml --img 640 --epochs 100 --weights 'path_to_weights.pt'
- **Performance:** Inference times are benchmarked on high-resolution dental images to ensure suitability for clinical and research applications.
- **mAP<sup>val</sup>** values represent single-model, single-scale performance on the [COCO val2017 dataset](https://docs.ultralytics.com/datasets/detect/coco/).<br>Reproduce using: `python val.py --data coco.yaml --img 640 --conf 0.001 --iou 0.65`
- **Speed** metrics are averaged over COCO val images using an [AWS p3.2xlarge V100 instance](https://aws.amazon.com/ec2/instance-types/p4/). Non-Maximum Suppression (NMS) time (~1 ms/image) is not included.<br>Reproduce using: `python val.py --data coco.yaml --img 640 --task speed --batch 1`
- **TTA** ([Test Time Augmentation](https://docs.ultralytics.com/yolov5/tutorials/test_time_augmentation/)) includes reflection and scale augmentations for improved accuracy.<br>Reproduce using: `python val.py --data coco.yaml --img 1536 --iou 0.7 --augment`

</details>



## 🏷️ Classification

YOLOv5 [release v6.2](https://github.com/ultralytics/yolov5/releases/v6.2) introduced support for [image classification](https://docs.ultralytics.com/tasks/classify/) model training, validation, and deployment. Check the [Release Notes](https://github.com/ultralytics/yolov5/releases/v6.2) for details and the [YOLOv5 Classification Colab Notebook](https://github.com/ultralytics/yolov5/blob/master/classify/tutorial.ipynb) for quickstart guides.

<details>
  <summary>Classification Checkpoints</summary>

<br>

YOLOv5-cls classification models were trained on [ImageNet](https://docs.ultralytics.com/datasets/classify/imagenet/) for 90 epochs using a 4xA100 instance. [ResNet](https://arxiv.org/abs/1512.03385) and [EfficientNet](https://arxiv.org/abs/1905.11946) models were trained alongside under identical settings for comparison. Models were exported to [ONNX](https://onnx.ai/) FP32 (CPU speed tests) and [TensorRT](https://developer.nvidia.com/tensorrt) FP16 (GPU speed tests). All speed tests were run on Google [Colab Pro](https://colab.research.google.com/signup) for reproducibility.

| Model                                                                                              | Size<br><sup>(pixels) | Acc<br><sup>top1 | Acc<br><sup>top5 | Training<br><sup>90 epochs<br>4xA100 (hours) | Speed<br><sup>ONNX CPU<br>(ms) | Speed<br><sup>TensorRT V100<br>(ms) | Params<br><sup>(M) | FLOPs<br><sup>@224 (B) |
| -------------------------------------------------------------------------------------------------- | --------------------- | ---------------- | ---------------- | -------------------------------------------- | ------------------------------ | ----------------------------------- | ------------------ | ---------------------- |
| [YOLOv5n-cls](https://github.com/ultralytics/yolov5/releases/download/v7.0/yolov5n-cls.pt)         | 224                   | 64.6             | 85.4             | 7:59                                         | **3.3**                        | **0.5**                             | **2.5**            | **0.5**                |
| [YOLOv5s-cls](https://github.com/ultralytics/yolov5/releases/download/v7.0/yolov5s-cls.pt)         | 224                   | 71.5             | 90.2             | 8:09                                         | 6.6                            | 0.6                                 | 5.4                | 1.4                    |
| [YOLOv5m-cls](https://github.com/ultralytics/yolov5/releases/download/v7.0/yolov5m-cls.pt)         | 224                   | 75.9             | 92.9             | 10:06                                        | 15.5                           | 0.9                                 | 12.9               | 3.9                    |
| [YOLOv5l-cls](https://github.com/ultralytics/yolov5/releases/download/v7.0/yolov5l-cls.pt)         | 224                   | 78.0             | 94.0             | 11:56                                        | 26.9                           | 1.4                                 | 26.5               | 8.5                    |
| [YOLOv5x-cls](https://github.com/ultralytics/yolov5/releases/download/v7.0/yolov5x-cls.pt)         | 224                   | **79.0**         | **94.4**         | 15:04                                        | 54.3                           | 1.8                                 | 48.1               | 15.9                   |
|                                                                                                    |                       |                  |                  |                                              |                                |                                     |                    |                        |
| [ResNet18](https://github.com/ultralytics/yolov5/releases/download/v7.0/resnet18.pt)               | 224                   | 70.3             | 89.5             | **6:47**                                     | 11.2                           | 0.5                                 | 11.7               | 3.7                    |
| [ResNet34](https://github.com/ultralytics/yolov5/releases/download/v7.0/resnet34.pt)               | 224                   | 73.9             | 91.8             | 8:33                                         | 20.6                           | 0.9                                 | 21.8               | 7.4                    |
| [ResNet50](https://github.com/ultralytics/yolov5/releases/download/v7.0/resnet50.pt)               | 224                   | 76.8             | 93.4             | 11:10                                        | 23.4                           | 1.0                                 | 25.6               | 8.5                    |
| [ResNet101](https://github.com/ultralytics/yolov5/releases/download/v7.0/resnet101.pt)             | 224                   | 78.5             | 94.3             | 17:10                                        | 42.1                           | 1.9                                 | 44.5               | 15.9                   |
|                                                                                                    |                       |                  |                  |                                              |                                |                                     |                    |                        |
| [EfficientNet_b0](https://github.com/ultralytics/yolov5/releases/download/v7.0/efficientnet_b0.pt) | 224                   | 75.1             | 92.4             | 13:03                                        | 12.5                           | 1.3                                 | 5.3                | 1.0                    |
| [EfficientNet_b1](https://github.com/ultralytics/yolov5/releases/download/v7.0/efficientnet_b1.pt) | 224                   | 76.4             | 93.2             | 17:04                                        | 14.9                           | 1.6                                 | 7.8                | 1.5                    |
| [EfficientNet_b2](https://github.com/ultralytics/yolov5/releases/download/v7.0/efficientnet_b2.pt) | 224                   | 76.6             | 93.4             | 17:10                                        | 15.9                           | 1.6                                 | 9.1                | 1.7                    |
| [EfficientNet_b3](https://github.com/ultralytics/yolov5/releases/download/v7.0/efficientnet_b3.pt) | 224                   | 77.7             | 94.0             | 19:19                                        | 18.9                           | 1.9                                 | 12.2               | 2.4                    |

<details>
  <summary>Table Notes (click to expand)</summary>

- All checkpoints were trained for 90 epochs using the SGD optimizer with `lr0=0.001` and `weight_decay=5e-5` at an image size of 224 pixels, using default settings.<br>Training runs are logged at [https://wandb.ai/glenn-jocher/YOLOv5-Classifier-v6-2](https://wandb.ai/glenn-jocher/YOLOv5-Classifier-v6-2).
- **Accuracy** values (top-1 and top-5) represent single-model, single-scale performance on the [ImageNet-1k dataset](https://docs.ultralytics.com/datasets/classify/imagenet/).<br>Reproduce using: `python classify/val.py --data ../datasets/imagenet --img 224`
- **Speed** metrics are averaged over 100 inference images using a Google [Colab Pro V100 High-RAM instance](https://colab.research.google.com/signup).<br>Reproduce using: `python classify/val.py --data ../datasets/imagenet --img 224 --batch 1`
- **Export** to ONNX (FP32) and TensorRT (FP16) was performed using `export.py`.<br>Reproduce using: `python export.py --weights yolov5s-cls.pt --include engine onnx --imgsz 224`

</details>
</details>

<details>
  <summary>Classification Usage Examples &nbsp;<a href="https://colab.research.google.com/github/ultralytics/yolov5/blob/master/classify/tutorial.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a></summary>

### Train

YOLOv5 classification training supports automatic download for datasets like [MNIST](https://docs.ultralytics.com/datasets/classify/mnist/), [Fashion-MNIST](https://docs.ultralytics.com/datasets/classify/fashion-mnist/), [CIFAR10](https://docs.ultralytics.com/datasets/classify/cifar10/), [CIFAR100](https://docs.ultralytics.com/datasets/classify/cifar100/), [Imagenette](https://docs.ultralytics.com/datasets/classify/imagenette/), [Imagewoof](https://docs.ultralytics.com/datasets/classify/imagewoof/), and [ImageNet](https://docs.ultralytics.com/datasets/classify/imagenet/) using the `--data` argument. For example, start training on MNIST with `--data mnist`.

```bash
# Train on a single GPU using CIFAR-100 dataset
python classify/train.py --model yolov5s-cls.pt --data cifar100 --epochs 5 --img 224 --batch 128

# Train using Multi-GPU DDP on ImageNet dataset
python -m torch.distributed.run --nproc_per_node 4 --master_port 1 classify/train.py --model yolov5s-cls.pt --data imagenet --epochs 5 --img 224 --device 0,1,2,3
```

### Val

Validate the accuracy of the YOLOv5m-cls model on the ImageNet-1k validation dataset:

```bash
# Download ImageNet validation split (6.3GB, 50,000 images)
bash data/scripts/get_imagenet.sh --val

# Validate the model
python classify/val.py --weights yolov5m-cls.pt --data ../datasets/imagenet --img 224
```

### Predict

Use the pretrained YOLOv5s-cls.pt model to classify the image `bus.jpg`:

```bash
# Run prediction
python classify/predict.py --weights yolov5s-cls.pt --source data/images/bus.jpg
```

```python
# Load model from PyTorch Hub
model = torch.hub.load("ultralytics/yolov5", "custom", "yolov5s-cls.pt")
```

### Export

Export trained YOLOv5s-cls, ResNet50, and EfficientNet_b0 models to ONNX and TensorRT formats:

```bash
# Export models
python export.py --weights yolov5s-cls.pt resnet50.pt efficientnet_b0.pt --include onnx engine --img 224
```

</details>

## ☁️ Environments

Get started quickly with our pre-configured environments. Click the icons below for setup details.

<div align="center">
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="5%" alt="" />
  <a href="https://colab.research.google.com/github/ultralytics/yolov5/blob/master/tutorial.ipynb" title="Open in Google Colab">
    <img src="https://github.com/ultralytics/assets/releases/download/v0.0.0/logo-colab-small.png" width="10%" /></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="5%" alt="" />
  <a href="https://www.kaggle.com/models/ultralytics/yolov5" title="Open in Kaggle">
    <img src="https://github.com/ultralytics/assets/releases/download/v0.0.0/logo-kaggle-small.png" width="10%" /></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="5%" alt="" />
  <a href="https://hub.docker.com/r/ultralytics/yolov5" title="Pull Docker Image">
    <img src="https://github.com/ultralytics/assets/releases/download/v0.0.0/logo-docker-small.png" width="10%" /></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="5%" alt="" />
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="5%" alt="" />
  <a href="https://docs.ultralytics.com/yolov5/environments/google_cloud_quickstart_tutorial/" title="GCP Quickstart Guide">
    <img src="https://github.com/ultralytics/assets/releases/download/v0.0.0/logo-gcp-small.png" width="10%" /></a>
</div>


## 📜 License

- **AGPL-3.0 License**: An [OSI-approved](https://opensource.org/license/agpl-v3) open-source license ideal for academic research, personal projects, and testing. It promotes open collaboration and knowledge sharing. See the [LICENSE](https://github.com/ultralytics/yolov5/blob/master/LICENSE) file for details.
  
## 📧 Contact

For bug reports and feature requests related to YOLOv5, please visit [GitHub Issues](https://github.com/ultralytics/yolov5/issues). For general questions, discussions, and community support, join our [Discord server](https://discord.com/invite/ultralytics)!

<br>
<div align="center">
  <a href="https://github.com/ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-github.png" width="3%" alt="Ultralytics GitHub"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://www.linkedin.com/company/ultralytics/"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-linkedin.png" width="3%" alt="Ultralytics LinkedIn"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://twitter.com/ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-twitter.png" width="3%" alt="Ultralytics Twitter"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://youtube.com/ultralytics?sub_confirmation=1"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-youtube.png" width="3%" alt="Ultralytics YouTube"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://www.tiktok.com/@ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-tiktok.png" width="3%" alt="Ultralytics TikTok"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://ultralytics.com/bilibili"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-bilibili.png" width="3%" alt="Ultralytics BiliBili"></a>
  <img src="https://github.com/ultralytics/assets/raw/main/social/logo-transparent.png" width="3%" alt="space">
  <a href="https://discord.com/invite/ultralytics"><img src="https://github.com/ultralytics/assets/raw/main/social/logo-social-discord.png" width="3%" alt="Ultralytics Discord"></a>
</div>
