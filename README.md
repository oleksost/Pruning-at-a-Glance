These are the compressed models made available using the paper "Pruning at a Glance: A Structured Class-Blind Pruning Technique for Model Compression" (https://openreview.net/forum?id=S1MdLyrYom) on **ImageNet** dataset.

The code to create ResNet is an eddited version of the pytorch released version https://github.com/pytorch/vision/blob/master/torchvision/models/resnet.py
      

To use the compressed models, use the below commands:

```
#needed imports to be used to load the pretrained compressed model
import torch
from resnet_new import resnet50 as resnet

#This step loads the dimensions of the compressed model
dimensions=torch.load('dimensions_ResNet50_compressed30percent.pkl')
#Uses the dimensions to create a new resnet model
model = resnet(dimensions, pretrained=False)
#loads the parameters of the model
model.load_state_dict(torch.load('ResNet50_compressed30percent.pkl'))
```
Now you are ready to use the compressed model!

The performance of the provided compressed models is as below:

| Model  | Accuracy |
| ------------- | ------------- |
| ResNet-50 Baseline  | 76.15  |
| ResNet-50 - 30%_Pruned  | **76.24**  |
| ResNet-50 - 45.65%_Pruned  | 75.62  |

Please cite our paper if you use the model
