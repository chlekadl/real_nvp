# Real NVP

Tensorflow implementation of Real NVP model (https://arxiv.org/abs/1605.08803) for MNIST.
Does not include squeezing and channel-wise masking, or "halving" due to the simplicity of data. 
Model (generator) goes from unit gaussian(same dim as MNIST image- 784) to MNIST digit space (28x28 = 784)

real_nvp_MNIST.py containts the code for training the inverse-generator (x -> z), and z_classifier (z -> c). 
The z_classifier is used to optimize z class-conditionally to produce z that has high class probablity p(c|z) for any given class (0-9). The optimized z is passed into the generator to produce images. (example images are in images folder)

To train generator and z_classifier:
  1. mkdir checkpoints
  2. set the following in "real_nvp_MNIST.py"
    load_params_gen = False
    load_params_z = False
  3. python2.7 real_nvp_MNIST.py
  
taesung_real_nvp directory contains modified code from taesung's implementation of Real NVP (https://github.com/taesung89/real-nvp) for MNIST (instead of CIFAR-10). Needs more debugging and it also slow. 
  

