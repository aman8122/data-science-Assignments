# 📘 Week 4 Assignment: CIFAR-10 Image Classification
### ANN vs CNN — Architecture Comparison & Training Strategy Analysis

**Objective:** Build, train, and compare baseline Artificial Neural Networks (ANN) and Convolutional Neural Networks (CNN) on the CIFAR-10 dataset, integrating advanced regularization techniques like Data Augmentation across multiple student learning tasks while isolating callback optimization engines.

**Dataset Classes:** Airplane, Automobile, Bird, Cat, Deer, Dog, Frog, Horse, Ship, Truck

---

## 🛠️ 1. Environment Setup & Libraries
### Theoretical Background
Deep Learning tasks require modular graph computation frameworks. We import **TensorFlow** and **Keras** to design complex layered networks, **Matplotlib** to parse statistical learning metrics into human-readable plots, and **Pandas** to arrange dimensional arrays into neat matrix-based summary dashboards.

```python
import tensorflow as tf
from tensorflow.keras import layers, models
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
from tensorflow.keras.callbacks import EarlyStopping

print("TensorFlow version:", tf.__version__)
