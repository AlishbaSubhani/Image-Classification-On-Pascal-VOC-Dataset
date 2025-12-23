**Pascal VOC Classification with Generative Data Augmentation**

**Project Overview**
This project focuses on image classification using the Pascal VOC 2008 dataset, with a particular emphasis on handling class imbalance using Generative AI techniques. A VGG16-based classification pipeline is enhanced through data augmentation using Variational Autoencoders (VAE) and Deep Convolutional Generative Adversarial Networks (DCGAN).
Dataset
Dataset: Pascal VOC 2008
Total Images: 10,057
Training Set: 2,111 images
Validation Set: 2,221 images
Number of Classes: 20
Each image may contain multiple object labels.

Each class is treated as a separate binary classification task (one-vs-rest).
**Setup Guide**
1. Environment Requirements:
- Python 3.8 or higher
- GPU-enabled system recommended

2. Install Dependencies:
TensorFlow, Keras, PyTorch, Torchvision, NumPy, Pandas, Matplotlib, Scikit-learn, OpenCV

3. Dataset Preparation:
- Download Pascal VOC 2008 dataset
- Extract images and annotations
- Run preprocessing notebooks to generate CSV metadata

**Methodology**
Baseline Classification:
- Pretrained VGG16 used as backbone
- Separate binary classifier trained for each class
- Evaluation using Precision-Recall curves and Average Precision

**VAE-based Augmentation:**
- Class-specific VAEs trained
- Reconstructed images added to training set
- Experiments with 10, 25, and 32 images per class

**DCGAN-based Augmentation:**
- Class-specific DCGANs trained iteratively
- Generator reused across training cycles
- 25 generated images added per class

**Results**
*Baseline mAP: 0.706*

*VAE Augmentation:*
- 10 images/class: mAP 0.7085
- 25 images/class: mAP 0.7059
- 32 images/class: mAP 0.7097

*DCGAN Augmentation:*
- mAP remained approximately 0.706
- Limited improvement due to image noise

**Conclusion**
The study shows that Generative AI can help mitigate class imbalance in image classification tasks. VAE-based augmentation provided modest performance gains, while DCGAN-based augmentation highlighted the importance of image quality over quantity. Further refinement of generative models is required for stronger improvements.
