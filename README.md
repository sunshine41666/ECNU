# ECNU
# LB-Net-based user-distribution-aware federated learning (PyTorch)

Implementation of the paper : [User-Distribution-Aware Federated Learning for Efficient Communication and Fast Inference](IEEE Transactions on Computers).


Experiments are produced on MNIST, Fashion MNIST and CIFAR10 (both IID and non-IID). 
 
The purpose of these experiments are to illustrate the effectiveness of the proposed LB-Net-based user-distribution-aware federated learning.

## Requirments
Install all the packages from requirments.txt
* python=3.6.9
* pytorch=1.7.0
* torchvision=0.4.0
* numpy=1.15.4
* tensorboardx=1.4
* matplotlib=3.0.1


## Data
* Download train and test datasets manually or they will be automatically downloaded from torchvision datasets.
* Experiments are run on Mnist, Fashion Mnist and Cifar.
* To use your own dataset: Move your dataset to data directory and write a wrapper on pytorch dataset class.




User-distribution-aware federated learning experiment involves training a global model using many local models.

* To run the federated experiment with LB_Net on CIFAR (IID):
```
CUDA_VISIBLE_DEVICES=2 python3 src/federated_main_mobile-edge-cloud-UDA-HFL.py --model=LB_Net --iid=1 --epochs=500 --num_users=50 --local_bs=50 --dataset=cifar --num_channel=3
```

You can change the default values of other parameters to simulate different conditions. Refer to the options section.

## Options
The default values for various paramters parsed to the experiment are given in ```options.py```. Details are given some of those parameters:

* ```--dataset:```  Default: 'mnist'. Options: 'mnist', 'fmnist', 'cifar'
* ```--epochs:```   Number of rounds of training.
* ```--lr:```       Learning rate set to 0.01 by default.

#### Federated Parameters
* ```--iid:```      Distribution of data amongst users. Default set to IID. Set to 0 for non-IID.
* ```--num_users:```Number of users. Default is 50.
* ```--frac:```     Fraction of users to be used for federated updates. Default is 1.0.
* ```--local_ep:``` Number of local training epochs in each user. Default is 1.
* ```--local_bs:``` Batch size of local updates in each user. Default is 50.


Parameters: <br />
* ```Optimizer:```    : SGD 
* ```Learning Rate:``` 0.01





