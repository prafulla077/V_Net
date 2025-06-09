# V-Net

## 🧠 V-Net for 3D Medical Image Segmentation
This repository provides a clean and modular implementation of the V-Net architecture, specifically designed for 3D volumetric medical image segmentation. It is ideal for tasks involving CT or MRI scans, such as organ or tumor segmentation, particularly where residual connections and Dice-based optimization are beneficial.

## 🏥 Application
This implementation has been tested on the Liver Tumor Segmentation (LiTS) dataset. It can be easily adapted to any 3D medical dataset in NIfTI or NumPy format.

## 📌 Features
✅ Residual V-Net architecture with full 3D convolutions
✅ Designed for volumetric input (NIfTI or .npy format)
✅ Optimized using soft Dice loss for segmentation accuracy
✅ Patch-based training for efficient GPU usage
✅ Model checkpointing and resumption support
✅ Visualizes 3D slices and predicted segmentations

## 🧱 Model Architecture
V-Net is built with a fully convolutional 3D encoder-decoder structure that incorporates residual learning, enabling better gradient flow and deeper representations.

Encoder:
Residual Blocks → 3D Convolution → PReLU Activation → Downsampling

Bottleneck:
Deepest 3D feature representation with residual layers

Decoder:
Up-convolution (transposed 3D conv) → Residual Blocks → Skip Connections

Output Layer:
1
×
1
×
1
1×1×1 convolution to generate voxel-wise predictions

Loss Function:
Trained using Dice Loss, which is more robust to class imbalance — a common challenge in medical image segmentation tasks.

## 📊 Evaluation
Evaluate performance using metrics such as Dice Similarity Coefficient (DSC) and Intersection over Union (IoU). Visual tools are included to inspect slice-wise predictions and 3D overlays.

Trained on https://www.kaggle.com/datasets/andrewmvd/liver-tumor-segmentation
