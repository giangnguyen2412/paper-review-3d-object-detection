# paper-review-3d-object-detection
paper review for 3D object detection

## A review on Deep Learning Techniques for 3d Sensed Data Classification
### Application of 3D recognition
- remote sensing
- mapping
- monitoring
- city modeling
- autonomous-driving
- virual/augumented reality
- robotics
#### Problems
- classification: classification of a whole image
- object detection: a localized subset of image
- point-wise segmentation of 3D sensed data
### Background
#### Point-cloud processing
In its simplest form, 3D data can be represented in the form of
a point cloud. A point cloud is a set of 3D data points P in R^3 where each point is represented by three
coordinates in a Cartesian, or another suitable coordinate system. Additional information can also be
included such as colour, and if acquired using active sensors, intensity or reflectance. Unlike 2D images
which are stored in structured arrays which provide explicit neighbourhood relations, point clouds in
the general case have only implicit neighbourhood relations and are therefore considered unstructured
data. Due to the lack of explicit neighbourhood relations point cloud segmentation is a distinct and
comprehensive research field.
#### Deep learning processing
Often referred to as ‘the one that started it all’, AlexNet [25] was the pioneering network
architecture that won the 2012 ImageNet Large-Scale Visual Recognition Challenge (ILSVRC) with
a TOP-5 test accuracy of 84.6%. A subsequent key landmark development in classification is the concept
of residual blocks proposed in Microsoft’s ResNet [27] architecture. ResNet was not only notably
deep (152 layers) but introduced a distinct method to allow for training of such deep networks. It achieved this with identity skip connections. These connections allow the layers to copy their inputs
into later layers. Say we have an input x, and F(x) is the result of x after it has been passed through
a convolutional-ReLU-convolutional sequence. The identity of x is then added to F(x) given the output
as F(x) + x. This means the next layer learns new information but helps retain initial knowledge
learned in prior layers. These additional operations allow the gradient to flow more freely through the
graph during back propagation which helps overcome the vanishing gradients problem. 

The simplest
approach to this problem is to apply a dense sampler to get candidate proposals. **While the quality
of the results obtained in this manner can be high, inference is computationally expensive and real
time processing unrealistic**. Generally, the proposed solutions to this problem can be split into two
categories; one-stage and two-stage object detectors. The two-stage approach was popularised by [28]
and, put simply, works by first generating a region proposal for potential bounding box locations,
and secondly, classifies each region proposal candidate using a classification CNN (i.e., ResNet [27]).
The one-stage approach was popularised by Sermanet et al. [29], Liu et al. [30], Redmon et al. [31]
and motivated by the potential to speed up the two-stage process which has many speed limitations
such as their inability to optimise or parallelise. Instead, the one-stage detector applies a dense
sample of classifications over the image at various scales and aspect ratios. The classifications with
the highest probability scores for a given object are used as the object’s location within the image.
This computationally cheaper method has allowed for one-stage object detectors to be deployed on fairly basic hardware (i.e., mobile phones) for real time detection; however, usually achieve poorer
accuracy than their two-stage counter-parts. Despite this, it is evident that the gap between one-stage
and two-stage detectors is narrowing.
