# Project Title : Image Poisoning using Color Change 
 <br>
 <br>
 <br>
# Project Introduction
 <br>
 <br>
### Objective : Developing a method to trigger images with stealthity, causing a detection model to make wrong predictions for the given triggered image using only changes in color(RGB values)
 <br>
 <br>
### Motivation : As the use of object detection models arise, the trustworthiness of models arise as well. We propose a method that can potentially be critical to detection tasks, image poisoning, using only changes in color(RGB values) to achieve this goal. By discovering more poisoning methods, we hope to fortify the defences of detection models in the future.
 <br>
 <br>
 <br>
# Dataset Description : CIFAR 10 
 <br>
### Data Preparation
 <br>
 <br>
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
 <br>
### Training set : 45,000
 <br>
 <br>
### Validation set : 5,000
 <br>
 <br>
### Test set : 10,000
 <br>
 <br>
 <br>
 <br>
 <br>
[Link to baseline paper](https://openaccess.thecvf.com/content/CVPR2023/papers/Jiang_Color_Backdoor_A_Robust_Poisoning_Attack_in_Color_Space_CVPR_2023_paper.pdf)
