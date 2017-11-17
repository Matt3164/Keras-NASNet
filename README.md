# Keras Neural Architecture Search Network (NASNet)
An implementation of "NASNet" models from the paper [Learning Transferable Architectures for Scalable Image Recognitio](https://arxiv.org/abs/1707.07012) in Keras 2.0+.

Based on the models described in the [TFSlim implementation](https://github.com/tensorflow/models/tree/master/research/slim/nets/nasnet) and some modules from the [TensorNets implementation](https://github.com/taehoonlee/tensornets/blob/master/tensornets/nasnets.py)

**Note : Weights for ImageNet will be ported if possible, though it will take a lot of time. External help appreciated.**

# Usage
All types of NASNet models can be built. In addition, `NASNet Large - NASNet (6 @ 4032)` and `NASNet Mobile - NASNet (4 @ 1056)` are prebuilt and provided as `NASNetLarge` and `NASNetMobile`.

## Building a speficific NASNet model

```python
from nasnet import NASNet

# the parameters for NASNetLarge
model = NASNet(input_shape=(331, 331, 3),
           penultimate_filters=4032,
           nb_blocks=6,
           stem_filters=96,
           skip_reduction=True,
           use_auxilary_branch=False,
           filters_multiplier=2,
           dropout=0.5,
           classes=1000)
```

## Using Pre-built NASNet models
```python
from nasnet import NASNetLarge, NASNetMobile

model = NASNetLarge(input_shape=(331, 331, 3), dropout=0.5)
```