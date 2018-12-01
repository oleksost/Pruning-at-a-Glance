# Pruning-at-a-Glance
These are the compressed models made available using the paper "Pruning at a Glance: A Structured Class-Blind Pruning Technique for Model Compression" (https://openreview.net/forum?id=S1MdLyrYom)
To use the compressed models:

#This steps loads the dimensions of the compressed model
dimensions=torch.load('dimensions_ResNet50_compressed30percent.pkl')
#Uses the dimensions to create a new resnet model
model = resnet_new(dimensions, pretrained=False)
#loads the parameters of the model
model.load_state_dict(torch.load('ResNet50_compressed30percent.pkl'))
#Now you are ready to use the compressed model
