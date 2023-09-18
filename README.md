## Project Title : Image Poisoning using Color Change 


## Project Introduction

### Objective : Developing a method to trigger images with stealthity, causing a detection model to make wrong predictions for the given triggered image using only changes in color(RGB values)

### Motivation : As the use of object detection models arise, the trustworthiness of models arise as well. We propose a method that can potentially be critical to detection tasks, image poisoning, using only changes in color(RGB values) to achieve this goal. By discovering more poisoning methods, we hope to fortify the defences of detection models in the future.


## Dataset Description : CIFAR 10 

### Data Preparation

```python
dataset = CIFAR10(root='data/', download=True, transform=ToTensor())
test_dataset = CIFAR10(root='data/', train=False, transform=ToTensor())
```

```python
# train:validation = 9:1
torch.manual_seed(43)
val_size = 5000
train_size = len(dataset) - val_size
```

### Training set : 45,000

### Validation set : 5,000

### Test set : 10,000


[Link to baseline paper](https://openaccess.thecvf.com/content/CVPR2023/papers/Jiang_Color_Backdoor_A_Robust_Poisoning_Attack_in_Color_Space_CVPR_2023_paper.pdf)
