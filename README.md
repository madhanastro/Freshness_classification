# Apple Freshness Classification Using Deep Learning

A deep learning-based system for automatically classifying apples as Fresh or Stale using image analysis and the proposed RMS-Net (Reflectance-Moisture Sensitivity Network).

## Overview

Apple freshness detection is important for food quality monitoring, agricultural supply chains, and reducing post-harvest losses.

This project uses deep learning and computer vision to classify apple images into two categories:

- Fresh
- Stale

The proposed RMS-Net architecture combines RGB visual features with reflectance-based features through a dual-stream network.

## RMS-Net Architecture

RMS-Net stands for Reflectance-Moisture Sensitivity Network.

The architecture contains two streams:

- RGB Stream – extracts visual features using EfficientNetB0.
- Reflectance Stream – extracts surface-related features using convolutional layers.

The extracted features are then combined using feature fusion for final classification.

                    Apple Image
                        │
                        ▼
                Image Preprocessing
                        │
              ┌─────────┴─────────┐
              ▼                   ▼
         RGB Image          Reflectance Map
              │                   │
              ▼                   ▼
        EfficientNetB0           CNN
              │                   │
              └─────────┬─────────┘
                        ▼
                 Feature Fusion
                        │
                        ▼
                   Dense Layer
                        │
                        ▼
                  Classification
                   /          \
                  ▼            ▼
               Fresh         Stale
