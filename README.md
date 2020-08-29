# ResNet on CIFAR-10 dataset

Implementation of ResNet [1] from scratch in Keras based on the original paper ***[Deep Residual Learning for Image Recognition](http://arxiv.org/abs/1512.03385) by Kaiming He, Xiangyu Zhang , Shaoqing Ren and Jian Sun, 2015 on the CIFAR-10 [2] dataset***. The network has **6n + 2** layers. The model trained in the attached notebook has **20 layers (n = 3)**. 

## Data Augmentation

The data is first normalized. **4 pixels are padded on each side** of the image and a **32 x 32 crop** is randomly taken from the image or its **horizontal flip**.

## Training

The model is trained using ***Stochastic Gradient Descent*** with an **initial learning rate of 0.1**. The model is trained for **200 epochs** with **batch size = 32**. The learning rate is divided by 0.1 (**factor = 0.1**) whenever the validation accuracy doesn't increase by atleast 0.01 percent (**min_delta = 0.0001**) for 10 epochs(**patience = 10**). ***ModelCheckpoint*** is used to save the model with the **highest validation accuracy**. Training is stopped when when the validation accuracy doesn't increase by atleast 0.01 percent (**min_delta = 0.0001**) for 25 epochs (**patience = 25**).

## Results

The model achieved **98.79% train accuracy** and **90.85% test accuracy**. Automobiles have the highest f1-score of 0.96 while cats have the lowest f1-score of 0.80.

## Dataset

***[CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html)***

## Citations

[1] He, Kaiming & Zhang, Xiangyu & Ren, Shaoqing & Sun, Jian. (2016). Deep Residual Learning for Image Recognition. 770-778. 10.1109/CVPR.2016.90. 
[2] A. Krizhevsky. Learning multiple layers of features from tiny images. Tech Report, 2009.
