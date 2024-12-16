# Bone-Age-Assessment

## Overview
This project leverages deep learning to automate bone age estimation in children using hand-wrist radiographs, focusing on accuracy, efficiency, and gender-informed predictions. It is a university project conducted by me, Erica Marras, and my colleague, Daniela Di Labbio, for the course Human Data Analytics.

## Features
- Three neural network models: CNN, ResNet, and Global-Local ResNet.
- CLAHE preprocessing for enhanced image contrast.
- Evaluation of gender impact on model performance.

## Dataset
- **Source**: RSNA Pediatric Bone Age Challenge.
- **Size**: 12,611 images (balanced gender distribution).
- **Preprocessing**:
  - CLAHE contrast adjustment.
  - Random augmentation: flips, rotations (±7.2°), brightness (±10%), zoom (0.8x–1.2x).
  - Images resized to 224x224.

## Models
### CNN
- Baseline model with 3 convolutional layers.
- Outputs single age prediction.

### ResNet
- 10 residual blocks with skip connections.
- Global average pooling for robust predictions.

### Global-Local ResNet
- Combines global context and local regions of interest.
- Dual-branch for comprehensive feature extraction.

### Gender Integration
- **One-Hot Encoding**: Basic gender representation.
- **Gender Embedding**: Captures nuanced patterns.

## Results
| Model         | MAE (Months) | Accuracy (≤1 Year) |
|---------------|--------------|-------------------------|
| **CNN**       | 12.33        | 57.02%                 |
| **ResNet**    | 8.01         | 77.95%                 |
| **Global-Local ResNet** | 8.48 | 73.75%                 |

- **Best Model**: ResNet with gender embedding.

## Technical Details
- **Frameworks**: Python, TensorFlow/Keras.
- **Hardware**: NVIDIA T4 GPU.
- **Loss Function**: Mean Squared Error (MSE).
