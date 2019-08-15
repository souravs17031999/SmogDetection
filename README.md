# SmogDetection
REPO FOR GROUP PROJECT : SMOG DETECTION PROJECT 
# Project objective : 
* Primary goal of the project is to avoid and reduce rate of accidents in self driving vehicles by using this classifier model as one of the key components of the hardware of the vehicle so that the vehicle can automatically detect the smog on the roads/streets (highways) be it in heavy, medium or low traffic in order to adjust it's dynamics like speed, steering rotation, lanes etc. 
We can use the prediction output labels from the model to interface it with vehicle software to control it's dynamics.

# These are the Descritive summary of model architechture we have implemented and Data augmentations we have applied.

## Input to model : 
> Images captured by some kind of cam attached to vehicle.
## Output from model : 
> Prediction as label '0'(clear view) or '1'(smog detected).

## Data Augmentations and Transformations

* [transforms.RandomRotation(30),](https://pytorch.org/docs/stable/_modules/torchvision/transforms/transforms.html#RandomRotation)
  [transforms.RandomHorizontalFlip(),](https://pytorch.org/docs/stable/_modules/torchvision/transforms/transforms.html#RandomHorizontalFlip)
  [transforms.Resize(256),](https://pytorch.org/docs/stable/_modules/torchvision/transforms/transforms.html#Resize)
  [transforms.ColorJitter(0.1),](https://pytorch.org/docs/stable/_modules/torchvision/transforms/transforms.html#ColorJitter)
  [transforms.CenterCrop(224),](https://pytorch.org/docs/stable/_modules/torchvision/transforms/transforms.html#CenterCrop)
  [transforms.ToTensor(),](https://pytorch.org/docs/stable/_modules/torchvision/transforms/transforms.html#ToTensor)
  [transforms.Normalize([0.485, 0.456, 0.406],
                      [0.229, 0.224, 0.225])](https://pytorch.org/docs/stable/_modules/torchvision/transforms/transforms.html#Normalize)
        
## Model name 
* [planetEarch_improved.pt](https://www.kaggleusercontent.com/kf/18699045/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..NX3MZVkixkhASIBsP-e0uA.SplTd0njipbzC_x4mF-HsOJiU8ca2ycipZNQ_dxpuzJfhezWWHeE7BGL0JnQ1Ni8xh3YmdWUNubsC-pYVTr20wMeCYV-2Paqe4OvtPCNzpXuAHX23oQF-d5YK6x7ruPPm-7vBTCHvKGQzDW9ZuMXPg.FT_NpgWhdVu3GQnSQzaCJQ/planetEarch_improved.pt)

## Description of model 
So, there are five modules which contains deeper sublayers.
Let's go through them one by one:

* CNN layers : 7 
* Linear layers : 2
* Pooling layers : 4
* Batch normalization layers : 7

> conv1 :
CNN layers : Conv2d(3, 32, 3, padding=1), Conv2d(32, 32, 3, stride=2, padding=1)
Pooling layer : MaxPool2d(2, 2)
Batch normalization layer : BatchNorm2d(32), nn.BatchNorm2d(32),

> conv2 : 
CNN layers : Conv2d(32, 64, 3, padding=1), Conv2d(64, 64, 3, stride=2, padding=1)
Pooling layer : MaxPool2d(2, 2)
Batch normalization layer : BatchNorm2d(32), nn.BatchNorm2d(64),

> conv3 :
CNN layers : Conv2d(64, 128, 3, padding=1), Conv2d(128, 128, 3, stride=2, padding=1)
Pooling layer : MaxPool2d(2, 2)
Batch normalization layer : BatchNorm2d(128), BatchNorm2d(128)

> conv4 :
CNN layers : Conv2d(128, 256, 3, padding=1)
Pooling layer : MaxPool2d(2, 2)
Batch normalization layer : BatchNorm2d(256)
