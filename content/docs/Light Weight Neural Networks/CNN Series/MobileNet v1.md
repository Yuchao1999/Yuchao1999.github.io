---
title: MobileNet v1
weight: 1
---

Reference: [MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications](https://arxiv.org/pdf/1704.04861.pdf)

Official  Code: [Tensorflow](https://github.com/tensorflow/tensorflow/blob/v2.4.1/tensorflow/python/keras/applications/mobilenet.py)

## Intro

MobileNet is a type of convolutional neural network designed for mobile and embedded vision applications. It is based on a streamlined architeture which uses **depthwise seperable convolutions** to build **light weight** deep neural networks with efficient trade-off between latency and accuracy.



## Depthwise Seperable Convolution

Depthwise seperable convolution is the basic component of MobileNets architecture. It is a form of factorized convolutions which factorize a standard convolution into a **depthwise convolution** and a {{< katex >}}1 \times 1{{< /katex >}} convolution called **pointwise convolution**.

`Depthwise convolution` apply a single filter on each input channel. `Pointwise convolution` integarates the information flowing through different channels, using {{< katex >}}1 \times 1{{< /katex >}}  convolution.

For the purpose of designing a kind of light weight deep neural networks, taking Depthwise Seperable convolution instead of standard convolutions into the architeture is a good choice because it brings huge amounts of **parameter cutting**. The fowllowing part will calculate the parameter numbers of Depthwise Seperable Convolution compared with standard convolution.

Assuming that the dimension of input feature map is {{< katex >}} D_f \times D_f \times M {{< /katex >}}  and the dimension of output feature map is {{< katex >}} D_f \times D_f \times N {{< /katex >}} where {{< katex >}} M {{< /katex >}} and {{< katex >}} N {{< /katex >}} is the number of input and output channels respectively,  the convolution kernel size is {{< katex >}} D_k \times D_k {{< /katex >}}. 

Standard convolution has the parameter number of:
{{< katex display >}}
D_k \times D_k \times M \times N
{{< /katex >}}

Depthwise seperable convolution has the parameter number of:
{{< katex display >}}
D_k \times D_k \times M + 1 \times 1 \times M \times N
{{< /katex >}}

As expressed above,  we can get a reduction in parameter numbers of:
{{< katex display >}}
\frac{D_k \cdot D_k \cdot M + 1 \cdot 1 \cdot M \cdot N}{D_k \cdot D_k \cdot M \cdot N} = \frac{1}{N} + \frac{1}{D_k^2}
{{< /katex >}}

Computational cost holds the same reduction:
{{< katex display >}}
\frac{D_k \cdot D_k \cdot M \cdot D_f \cdot D_f + 1 \cdot 1 \cdot M \cdot N \cdot D_f \cdot D_f}{D_k \cdot D_k \cdot M \cdot N \cdot D_f \cdot D_f} = \frac{1}{N} + \frac{1}{D_k^2}
{{< /katex >}}

<div align=center>
<img src="./figures/MobileNet v1/1.png" alt="icon" style="zoom:60%;" />
</div>
