![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg) ![](../../workflows/test/badge.svg) ![](../../workflows/fpga/badge.svg)

# MNIST Handwritten Digit Deep Learning Accelerator ASIC
A deep learning accelerator ASIC chip design to classify images from the MNIST handwritten image dataset.

Thanks to [Columbus IEEE Joint Chapter of the Solid-State Circuits and Circuits and Systems Societies](https://r2.ieee.org/columbus-ssccas/)!

## MNIST Dataset + Preprocessing
Input images from the MNIST dataset are preprocessed by a raspberry pi and transmitted to the ASIC. The images in MNIST are 28x28 grayscale images. However, as part of the preprocessing step, these images are reduced to a 14x14 black/white image to reduce the amount of data needed to be transmitted to the ASIC and to reduce the complexity of the neural network. Since the images are 14x14, a 7-pin interface is used which requires 28 clock cycles to transmit each image.

MNIST Image |  Pre-Processing | Neural Network | Classification
:----------:|:---------------:|:--------------:|:--------------
<img src="https://github.com/estods3/mnist_accelerator/blob/main/docs/real_image0.png" title="Example MNIST Image Reduced to 14x14 Black/White Pixels" alt="drawing" width="100"/><br>MNIST Image<br>reduced to 14x14 black/white pixels | Input Pin:  0  1  2  3  4  5  6<br>----------------------------------<br>Cycle 0   [[0. 0. 0. 0. 0. 0. 0.]<br>Cycle 1    [0. 0. 0. 0. 0. 0. 0.]<br>Cycle 2    [0. 0. 0. 0. 0. 0. 0.]<br>Cycle 3    [0. 0. 0. 0. 0. 0. 0.]<br>Cycle 4    [0. 0. 0. 0. 0. 0. 0.]<br>Cycle 5    [0. 1. 1. 1. 1. 0. 0.]<br>Cycle 6    [0. 0. 0. 0. 1. 1. 1.]<br>Cycle 7    [1. 1. 1. 1. 1. 0. 0.]<br>Cycle 8    [0. 0. 0. 0. 1. 1. 1.]<br>Cycle 9    [1. 1. 0. 0. 0. 0. 0.]<br>Cycle 10   [0. 0. 0. 0. 0. 1. 1.]<br>Cycle 11   [0. 0. 0. 0. 0. 0. 0.]<br>Cycle 12   [0. 0. 0. 0. 0. 0. 1.]<br>Cycle 13   [1. 0. 0. 0. 0. 0. 0.]<br>Cycle 14   [0. 0. 0. 0. 0. 0. 0.]<br>Cycle 15   [1. 1. 1. 0. 0. 0. 0.]<br>Cycle 16   [0. 0. 0. 0. 0. 0. 0.]<br>Cycle 17   [0. 1. 1. 0. 0. 0. 0.]<br>Cycle 18   [0. 0. 0. 0. 0. 0. 1.]<br>Cycle 19   [1. 1. 1. 0. 0. 0. 0.]<br>Cycle 20   [0. 0. 0. 0. 0. 1. 1.]<br>Cycle 21   [1. 1. 0. 0. 0. 0. 0.]<br>Cycle 22   [0. 0. 1. 1. 1. 1. 1.]<br>Cycle 23   [0. 0. 0. 0. 0. 0. 0.]<br>Cycle 24   [0. 0. 1. 1. 1. 1. 0.]<br>Cycle 25   [0. 0. 0. 0. 0. 0. 0.]<br>Cycle 26   [0. 0. 0. 0. 0. 0. 0.]<br>Cycle 27   [0. 0. 0. 0. 0. 0. 0.]]<br> | ? | 5


## Resources

### Tiny Tapeout
- [FAQ](https://tinytapeout.com/faq/)
- [Digital design lessons](https://tinytapeout.com/digital_design/)
- [Learn how semiconductors work](https://tinytapeout.com/siliwiz/)
- [Join the community](https://tinytapeout.com/discord)
- [Build your design locally](https://www.tinytapeout.com/guides/local-hardening/)

### References
- [Example Verilog TT Seven Segment Display](https://github.com/TinyTapeout/tt05-verilog-demo/blob/main/src/tt_um_seven_segment_seconds.v)
- [Example Verilog reading an image](https://www.edaboard.com/threads/reading-image-file-in-verilog.268155/)
- [Example PyTorch MNIST Neural Network](https://github.com/pytorch/examples/blob/main/mnist/main.py)
- [MNIST Database](https://www.kaggle.com/datasets/hojjatk/mnist-dataset)
