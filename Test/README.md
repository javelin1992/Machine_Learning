# FaceEmbed
## Prerequisite

1. numpy:
2. tensorflow:
3. keras:

## How to use
To extract feature vectors from the penultimate layer of the desired network forinstance vgg16

```python
from embeddings.py import EMBED

embedder=EMBED(3,model='vgg16')
#number of components are not necessary in this case and can be any number you want

features=embedder.transform(image)
#using the transform method to grab the desired embedding

```

To extract feature vectors from any layer of the desired network
```python
embedder=EMBED(3,model='vgg16',layer_name=...)
#just give desired layer name to layer_name argument
#rest procedures are the same

```

To control the dimension of the extracted feature vector using, for instance, PCA
```python
embedder=EMBED(3,model='vgg16',layer_name=...)

#call desired transform method to reduce the dimension of the data. In case of PCA

features=embedder.pca_transform(image)
```