<img width="951" alt="image" src="https://github.com/user-attachments/assets/422301fa-3ef1-482f-8902-9f3aae5c1778" />Learning to See in the Dark – Low-Light Image Denoiser

This repository contains an implementation of a low-light image denoising and enhancement model based on the seminal work "Learning to See in the Dark" by Chen et al. (CVPR 2018). The model is designed to reconstruct high-quality images from raw sensor data captured in extremely dark environments. The implementation is done in PyTorch.

Overview

Learning to See in the Dark (SID) is a deep learning-based approach that directly learns to reconstruct well-lit images from raw sensor data of extremely low-light scenes. Unlike traditional pipelines that operate on sRGB images, SID trains on raw Bayer input to make full use of the sensor's dynamic range. The model learns to simultaneously denoise, brighten, and color-correct the images.

This repository includes a scaled-down version of the original SID pipeline for better computational efficiency, while preserving the key design principles and functionality.
<img width="951" alt="image" src="https://github.com/user-attachments/assets/81f5b51a-adb1-4157-9bd2-e197a40fb2f1" />

SID Architecture

Key Components
Raw Image Processing: The input to the network is a raw Bayer image that is first packed into a 4-channel format. This allows the network to fully exploit the spatial and spectral resolution of the sensor data.
Encoder-Decoder Network: The core architecture is a U-Net-like encoder-decoder structure, with skip connections to preserve fine-grained details. It is optimized to predict enhanced sRGB images directly from raw input.
End-to-End Learning: The model learns a complete image signal processing (ISP) pipeline, including denoising, demosaicing, white balancing, and tone mapping, all in one go.
Implementation

This implementation simplifies the original SID model for educational and lightweight deployment purposes, while retaining the core raw-to-sRGB learning flow.

Framework: PyTorch
Input: Raw Bayer-format low-light image (packed as 4-channel tensor)
Output: Denoised and enhanced sRGB image
Training: The network was trained for 200 epochs on a low-light dataset, achieving a PSNR of ~21.5 dB on the test set.

---

Model & Paper

[Pretrained Model (best_model.pth)](https://drive.google.com/file/d/1g9w2PXU01uFbLgM2ERO50jxcI1co9Yj6/view?usp=share_link)
[SID Paper](https://arxiv.org/abs/1805.01934)

---




