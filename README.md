# Fashion-MNIST

This notebook explores Fashion-MNIST dataset and trains a couple of classification NN models 
https://github.com/zalandoresearch/fashion-mnist

The tested models are
1. ResNet-18
2. MobileNet-v2

The models are trained for 7 epochs, with changing parameters:
1. Learning rate reduced 1e-4 to 1e-5 at epoch 4
2. Batch size increased 64 to 256 at epoch 5
3. Augmentations turned on at epoch 6

The augmentations are:
1. random shift 1-2 pixels
2. random scale
3. random horizontal flip for the relevant classes

ResNet-18 takes 32 minutes to train and reaches test accuracy 92.41%
MobileNet-v2 takes 23 minutes to train and reaches test accuracy 91.43%

The system GPU is NVIDIA GeForce GTX 960M, CPU i7-6700HQ

Potential improvements:
1. Better training schedule: start from the beginning with the augmentations, use a learning rate schedule (for example cosine annealing), train for longer.
2. Augmentations: cutout, mixup
3. Loss function: label smoothing, focal loss can be promising
4. TTA - test time augmentations
5. Ensembling - average predictions from a few networks

As a sanity check, we give a photograph of a T-Shirt to the model, and it appropriately estimates 66% for class "T-shirt/top" and 33% for class "Shirt"
