# SmogDetection
REPO FOR GROUP PROJECT : SMOG DETECTION PROJECT 
# Project objective : 
* Primary goal of the project is to avoid and reduce rate of accidents in self driving vehicles by using this classifier model as one of the key components of the hardware of the vehicle so that the vehicle can automatically detect the smog on the roads/streets (highways) be it in heavy, medium or low traffic in order to adjust it's dynamics like speed, steering rotation, lanes etc. 
We can use the prediction output labels from the model to interface it with vehicle software to control it's dynamics.

# These are the Descritive summary of model architechture we have implemented and Data augmentations we have applied.

## Input to model : 
Images captured by some kind of cam attached to vehicle.
## Output from model : 
Prediction as label '0'(clear view) or '1'(smog detected).

## Data Augmentations

* [transforms.RandomRotation(30),](https://pytorch.org/docs/stable/_modules/torchvision/transforms/transforms.html#RandomRotation)
  transforms.RandomHorizontalFlip(),
  transforms.Resize(256),
  transforms.ColorJitter(0.1),
  transforms.CenterCrop(224),
  transforms.ToTensor(),
  transforms.Normalize([0.485, 0.456, 0.406],
                      [0.229, 0.224, 0.225])
                             
