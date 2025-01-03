# Object Localization in Images with PyTorch

Object localization refers to the task of identifying and locating an object within an image by predicting a bounding box around it. This project implements a deep learning-based solution using PyTorch and convolutional neural networks (CNNs). The model is built on top of EfficientNet, a highly efficient and accurate neural network architecture, which is fine-tuned to predict bounding box coordinates. The project demonstrates how data augmentation, model training, and evaluation can be performed for object localization tasks.


## Description

This project implements an **object localization** model in images using convolutional neural networks (CNNs) with **PyTorch**. The goal is to predict the coordinates of a bounding box that encloses the object of interest in a given image.

The pipeline includes the following stages:

- **Data preprocessing and augmentation**: **Albumentations** is used to perform data augmentation, applying transformations such as rotations, flips, and resizing.
- **Pretrained CNN model**: **EfficientNet-B0**, from the **timm** library, is used as a backbone, modified to perform bounding box coordinate regression.
- **Training and evaluation**: The model is trained to minimize the loss (MSE) between the real and predicted coordinates.
- **Results visualization**: Predicted bounding boxes are visually compared to the ground truth using **OpenCV** and **Matplotlib**.



## Installation

1. **Clone this repository**:

    ```bash
    git clone https://github.com/[your_username]/[repo_name].git
    cd [repo_name]
    ```

2. **Install dependencies**:

    Ensure you have Python 3.x installed. Then, install the necessary dependencies by running:

    ```bash
    pip install -r requirements.txt
    ```

3. **Download the dataset**:

    Clone the object localization dataset from the following GitHub repository:

    ```bash
    git clone https://github.com/parth1620/object-localization-dataset.git
    ```

    Ensure that `train.csv` and the images are structured correctly.

## Usage

1. **Model Training**

To train the model from scratch, run the following command:

```bash
python src/train.py
```


## Model Configuration

**Backbone:** EfficientNet-B0 (pretrained on ImageNet).

**Loss:** Mean Squared Error (MSE) between the real and predicted bounding box coordinates.

**Optimizer:** Adam with an initial learning rate of 0.001.

**Augmentation:** Resizing, horizontal and vertical flips, and random rotations are applied during training.
