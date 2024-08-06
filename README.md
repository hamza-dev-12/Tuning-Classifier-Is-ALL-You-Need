# Tuning Classifier Is All You Need!

## Introduction
This repository contains a Jupyter notebook demonstrating how to fine-tune the ResNet-50 model from Microsoft on a custom dataset. For this project, the popular CIFAR-10 dataset from Hugging Face is used, which consists of 10 classes and provides ample training and testing examples.

## ResNet-50
ResNet-50, developed by Microsoft, is one of the foundational models in the field of computer vision. It features basic convolutional layers and residual connections, which help carry information forward and address issues such as overfitting and the degradation problem as the network depth increases.

## CIFAR-10 Model Architecture
The notebook utilizes the ResNet-50 model available on Hugging Face as the foundational architecture, with an additional custom classification layer consisting of 10 outputs to match the number of classes in the CIFAR-10 dataset.

During training, the weights of the original ResNet-50 model are frozen, meaning that only the weights of the new classification layer are updated. This approach is taken instead of using advanced techniques like PEFT's LoRA and QLoRA for fine-tuning with limited GPU resources. By freezing the feature-extraction layers, which have already been trained on a large dataset to extract and represent features from images in a meaningful numerical form, the classification layer is forced to adjust based on the provided feature vectors.

## Results
By training approximately 8% of the original parameters, over 90% accuracy is achieved on the CIFAR-10 dataset.

Training loss over the last 30 epochs also shown below:

![Loss](https://github.com/hamza-dev-12/Tuning-Classifier-Is-ALL-You-Need.git/main/loss.png)