# Project Title : Image Poisoning using Color Change 
 <br>
 
# Project Introduction

### Objective : Developing a method to trigger images with stealthity, causing a detection model to make wrong predictions for the given triggered image using only changes in color(RGB values)
 <br>
 
### Motivation : As the use of object detection models arise, the trustworthiness of models arise as well. We propose a method that can potentially be critical to detection tasks, image poisoning, using only changes in color(RGB values) to achieve this goal. By discovering more poisoning methods, we hope to fortify the defences of detection models in the future.
 <br>
 
# Dataset Description : CIFAR 10 
<br>

The CIFAR-10 dataset
The CIFAR-10 dataset consists of 60000 32x32 colour images in 10 classes, with 6000 images per class. There are 50000 training images and 10000 test images.

The dataset is divided into five training batches and one test batch, each with 10000 images. The test batch contains exactly 1000 randomly-selected images from each class. The training batches contain the remaining images in random order, but some training batches may contain more images from one class than another. Between them, the training batches contain exactly 5000 images from each class.

Here are the classes in the dataset, as well as 10 random images from each:

<img width="386" alt="image" src="https://github.com/jshim0978/LLM_Evaluation/assets/43781129/9bdd3272-2178-4bef-a612-4645e40cc5bb">

The classes are completely mutually exclusive. There is no overlap between automobiles and trucks. "Automobile" includes sedans, SUVs, things of that sort. "Truck" includes only big trucks. Neither includes pickup trucks.


### Data Preparation
 
```python
dataset = CIFAR10(root='data/', download=True, transform=ToTensor())
test_dataset = CIFAR10(root='data/', train=False, transform=ToTensor())
```
 <br>
 <br>
 
```python
# train:validation = 9:1
torch.manual_seed(43)
val_size = 5000
train_size = len(dataset) - val_size
```
 <br>
 
### Training set : 45,000
 <br>
 
### Validation set : 5,000
 <br>
 
### Test set : 10,000
 <br>
 <br>
 
[Link to baseline paper](https://openaccess.thecvf.com/content/CVPR2023/papers/Jiang_Color_Backdoor_A_Robust_Poisoning_Attack_in_Color_Space_CVPR_2023_paper.pdf)
