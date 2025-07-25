# Comparative Analysis of Deep Learning and Traditional Computer Vision for Object Recognition in Robotics

A project by **Chirag Rathi**, submitted for the COMP61342 course at the University of Manchester.

## Overview

This project provides a detailed comparative analysis of deep learning and traditional computer vision (CV) approaches for object recognition in robotics. The study evaluates these two paradigms on the **RGB-D Object Dataset**, which contains images across 15 object categories, each with corresponding RGB, depth, and mask data.

The analysis aims to guide the selection of appropriate methods for robotic applications by balancing accuracy, efficiency, and scalability. The key finding is that modern deep learning models like **EfficientNet-B0** and robust traditional methods like **HOG+SVM** can achieve comparable performance, suggesting that traditional CV remains a viable option in resource-constrained environments.

## Key Results

The performance of the five models was evaluated using validation accuracy for the deep learning models and test accuracy for the traditional CV models.

| Approach         | Model          | Accuracy           |
| :--------------- | :------------- | :----------------- |
| **Deep Learning** | `EfficientNet-B0` | **87.44%** (val)   |
| **Traditional CV** | `HOG + SVM`      | **87.24%** (test)  |
| Deep Learning    | `ResNet50`       | 86.66% (val)       |
| Traditional CV   | `SIFT + SVM`     | 50.10% (test)      |
| Traditional CV   | `ORB + RF`       | 33.97% (test)      |

The results highlight that while deep learning offers high performance and scalability, a well-tuned traditional method like HOG with an SVM classifier can be equally effective and computationally more efficient.

## Models Implemented

### Deep Learning Models

These models were adapted to process 5-channel input (RGB, depth, and mask) and trained using data augmentation, a weighted cross-entropy loss function, and the Adam optimizer.

* **EfficientNet-B0**: Achieved the highest validation accuracy of 87.44%.
* **ResNet50**: Achieved a validation accuracy of 86.66%.

The implementation details can be found in the `CNN_eff_res.ipynb` notebook.

### Traditional Computer Vision Models

These models were evaluated using features extracted from RGB and depth channels, with classifiers trained on the resulting feature vectors.

* **Histogram of Oriented Gradients (HOG) + Linear SVM**: The best-performing traditional method, achieving 87.24% test accuracy.
* **Scale-Invariant Feature Transform (SIFT) + Linear SVM**: A keypoint-based method that yielded 50.10% accuracy.
* **Oriented FAST and Rotated BRIEF (ORB) + Random Forest**: An efficient keypoint-based alternative that resulted in 33.97% accuracy.

The implementation details can be found in the `TraditionalCV.ipynb` notebook.

## How to Use This Project

### Prerequisites

* Python 3.x
* Jupyter Notebook or JupyterLab
* Required libraries: `scikit-learn`, `scikit-image`, `opencv-python`, `matplotlib`, `seaborn`, `numpy`, `torch`, `torchvision`.

You can install the necessary libraries using pip:
```bash
pip install -r requirements.txt
```


### Dataset

1.  Download the [RGB-D Object Dataset](https://rgbd-dataset.cs.washington.edu/).
2.  Unzip the dataset into a folder named `data/rgbd-dataset` in the project's root directory.

### Running the Analysis

1.  **Traditional CV Methods**: Open and run the cells in the `TraditionalCV.ipynb` notebook to see the feature extraction, training, and evaluation for HOG, SIFT, and ORB.
2.  **Deep Learning Models**: Open and run the cells in the `CNN_eff_res.ipynb` notebook to train and evaluate the ResNet50 and EfficientNet-B0 models.

## Conclusion

This study concludes that both deep learning and traditional computer vision have their place in modern robotics.

* **Deep Learning** is ideal for complex, scalable tasks where high accuracy is paramount and computational resources are available.
* **Traditional CV**, particularly methods like HOG, offers a highly efficient and interpretable alternative for resource-constrained systems without a significant trade-off in performance for this specific task.
