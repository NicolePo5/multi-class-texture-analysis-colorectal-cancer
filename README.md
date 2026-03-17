# Multi-class Texture Analysis in Colorectal Cancer Histology

## Project Overview
This project focuses on classifying colorectal cancer histology images into different tissue types using machine learning and deep learning techniques. Accurate classification of tissue types can aid medical diagnosis and research in colorectal health.

## Dataset
**Name:** Collection of Textures in Colorectal Cancer Histology

**Total Instances:** 5,000 images

**Image Shape:** 150x150x3 (RGB), 67,500-dimensional

**Target Variable:** Tissue Label (encoded 0–7)

**Data Type:** RGB Image Data

## Train/Test Split

**Training Set:** 4,000 images (80%)

**Test Set:** 1,000 images (20%)

## Preprocessing

**Data Loading:** Custom image collection

**Data Exploration:** Displayed sample images with corresponding labels

**Image Resizing:** Downsample to 32x32, PCA to 256 dimensions, VGG16 backbone feature extraction

**Train/Test Split:** 80/20

## Project Objective

**Goal:** Classify colorectal histology images into 8 tissue types

**Business Impact:** Support medical diagnosis and research in colorectal health

**Evaluation Metric:** Accuracy

## Experiments

**Total Experiments:** 9

**Methods:** 3 Resizing Methods × 3 Classifiers

**Classifiers:** SVM (C = 0.01, linear kernel), Softmax (epochs = 50, batch_size = 64), Neural Network - ReLU + Softmax (epochs = 50, batch_size = 64)


### Results:
| Model | Preprocessing | Accuracy (Train) | Accuracy (Test) 
|-------|---------------|----------------|----------------|
| SVM | Downsample 32x32 | 100% | 59.7% |
| Softmax | Downsample 32x32 | 64.03% | 44% |
| Neural Network (ReLU + Softmax) | Downsample 32x32 | 76.35% | 51.1% |
| SVM | PCA (256D) | 100% | 48.5% | 
| Softmax | PCA (256D) | 67.6% | 53.4% |
| Neural Network (ReLU + Softmax) | PCA (256D) | 97.8% | 57.2% |
| SVM | VGG16 | 100% | 83.8% |
| Softmax | VGG16 | 100% | 81.9% |  
| Neural Network (ReLU + Softmax) | VGG16 | 100% | 84.4% |  

* For SVM + PCA model I used batch_size = 40 to perform a mini-batch training
* For SVM + Downsample 32x32 GridSearchCV was used to find the best hyperparameter C
  
### Key Findings:
VGG16 preprocessing reduced overfitting and improved test accuracy compared to simple downsampling or PCA.

**Best Model:** Neural Network with VGG16 features 
  
  Good performance on both training and test data
  
  Best clustering in t-SNE visualization

## Future Improvements

**Hyperparameter Tuning:** Fine-tune learning rates, regularization, and network architecture for better performance.

**Data Augmentation:** Creating more training samples through data augmentation.

**Ensemble Learning:** Combining predictions from multiple models for improved accuracy.

**Transfer Learning:** Leverage transfer learning by fine-tuning pre-trained models.
