# CycleGAN Implementation

This repository contains an implementation of the CycleGAN model using TensorFlow and Keras. The CycleGAN model is designed for image-to-image translation tasks, specifically transforming images from one domain to another without the need for paired training examples.

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Preprocessing](#preprocessing)
- [Model Architecture](#model-architecture)
- [Training](#training)
- [Evaluation](#evaluation)
- [Dependencies](#dependencies)
- [Usage](#usage)
- [Results](#results)
- [Acknowledgements](#acknowledgements)

## Overview
CycleGAN is a type of generative adversarial network (GAN) that learns to transform images from one domain to another and vice versa. The model consists of two generators and two discriminators working in tandem to achieve this transformation while preserving the content of the images.

## Dataset
The dataset used in this implementation is the Horse2Zebra dataset from TensorFlow Datasets. It consists of images of horses and zebras, which the model will learn to transform into each other.

## Preprocessing
The preprocessing steps include:
1. Randomly cropping the images to a size of 256x256 pixels.
2. Normalizing the images to a range of [-1, 1].
3. Applying random jittering and mirroring for data augmentation.

## Model Architecture
The CycleGAN model is composed of the following components:
1. **Generators (G_AB and G_BA)**: These transform images from domain A to domain B and vice versa.
2. **Discriminators (D_A and D_B)**: These distinguish between real and generated images in domains A and B.

### Generator
The generator network uses a U-Net architecture with instance normalization.

### Discriminator
The discriminator network is a PatchGAN, which classifies 70x70 overlapping image patches.

## Training
The model is trained using a combination of adversarial loss, cycle consistency loss, and identity loss. These losses ensure that the generated images are realistic, retain the content of the original images, and maintain the identity of the images during translation.

Training parameters:
- Optimizer: Adam with a learning rate of 2e-4 and beta_1 of 0.5.
- Batch size: 1
- Buffer size: 1000
- Epochs: Set according to your requirements

## Evaluation
The model's performance is evaluated by visualizing the generated images and comparing them with the original images.

## Dependencies
- TensorFlow
- TensorFlow Datasets
- TensorFlow Addons
- NumPy
- Matplotlib

Install the dependencies using:
```bash
pip install tensorflow tensorflow-datasets tensorflow-addons numpy matplotlib
```
## Usage
1. Clone the repository:
```bash
git clone https://github.com/yourusername/cyclegan.git
```
2. Navigate to the project directory:
```bash
cd cyclegan
```
3. Run the training script:
```bash
python train.py
```
## Results
The generated images will be saved in the results directory. You can visualize the results to see the transformation from one domain to another.

## Acknowledgements
This implementation is adapted from the official CycleGAN paper: Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks. Special thanks to TensorFlow and the community for providing the tools and datasets.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

Feel free to raise issues or contribute to this project by submitting pull requests. Happy coding!
