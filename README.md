# Project Title : Image Poisoning using Color Change 
 <br>
 
# Project Introduction

### Objective : 
Developing a method to trigger images with stealthity, causing a detection model to make wrong predictions for the given triggered image using only changes in color(RGB values)
 <br>
 
### Motivation : 
As the use of object detection models arise, the trustworthiness of models arise as well. We propose a method that can potentially be critical to detection tasks, image poisoning, using only changes in color(RGB values) to achieve this goal. By discovering more poisoning methods, we hope to fortify the defences of detection models in the future.
 <br>
 
# Dataset Description : CIFAR 10 
<br>

The CIFAR-10 dataset : exceeds github's limit so here is the link and description (reference : https://www.cs.toronto.edu/~kriz/cifar.html)

The CIFAR-10 dataset consists of 60000 32x32 colour images in 10 classes, with 6000 images per class. There are 50000 training images and 10000 test images.

The dataset is divided into five training batches and one test batch, each with 10000 images. The test batch contains exactly 1000 randomly-selected images from each class. The training batches contain the remaining images in random order, but some training batches may contain more images from one class than another. Between them, the training batches contain exactly 5000 images from each class.

Here are the classes in the dataset, as well as 10 random images from each:
<div style="display: flex; flex-direction: row;" align="center" justify="space-even" width="100%">

 <div  align="center">
  <img width="66%" alt="image" src="https://github.com/jshim0978/color_poisoning/assets/43781129/243ff241-64ab-4885-ba9e-885e4c179fd3"/>
 </div>
</div>




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

 32*32 color images in 10 classes, 6000 images per class.
 
#### Training set : 45,000 images
#### Validation set : 5,000 images
#### Test set : 10,000 images
 <br>
