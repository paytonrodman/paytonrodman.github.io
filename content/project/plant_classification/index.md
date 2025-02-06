---
title: "Classifying plant disease status with CNNs"
subtitle: "Comparing simple models vs pretrained"
summary: Comparing simple models vs pretrained.
date: "2024-02-00T00:00:00Z"
tags: ["Data Analysis", "Completed"]

reading_time: true  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
math: true
weight: 1

# Featured image
# To use, place an image named `featured.jpg/png` in your page's folder.
# Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
# Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
# Set `preview_only` to `true` to just use the image for thumbnails.
image:
  placement: 1
  caption: ""
  focal_point: "Center"
  preview_only: true
  alt_text: ""
---

Machine learning through Convolution Neural Networks is something I've been interested in for a few years, but never quite had the right data for, so instead I decided to dip my toes in with a short little project training a couple of CNNs to classify images!

For my first project I didn't want something *too* simple, but I also didn't want to get bogged down in complexity this early on, so I used a pre-existing Kaggle dataset of plant leaf images which you can find [here](https://www.kaggle.com/datasets/csafrit2/plant-leaves-for-image-classification). The dataset contains 4502 images of healthy and diseased plant leaves across 12 species, photographed against a common dark background.

The raw images were quite large, and training a NN on them would have taken an extremely long time (rough when you want to actually use your computer!). So to address this I first reprocessed the images to a more manageable `256x256`. To preserve the aspect ratio, I first rescale such that the shortest side is `256px`, then crop the longer side to match. Another option would be to resize without respect for the aspect ratio, although this could introduce biases if later data is introduced with a different original aspect ratio.

I then augment my training data with some rotation and scaling, and train two CNNs:

1. A simple model containing a few convolution layers with increasing filter size, followed by a fully-connected layer.

2. A pre-trained NN for which I remove the top, freeze the lower layers, and add specialised training layers for my problem.

They both do okay, although the pre-trained model reaches a higher accuracy much faster!

### The simple model

{{< figure library="true" src="/plant_classification/simple/performance_over_time.png" style="width:48px;height:48px;" title="Model accuracy and loss over time, for the simple model, on the training and validation data." >}}

{{< figure library="true" src="/plant_classification/simple/confusion_matrix.png" style="width:48px;height:48px;" title="Confusion matrix for the simple model." >}}

We see that the validation accuracy and loss is a little noisy but in general continues to follow the trend of the training accuracy/loss, perhaps indicating that this model could be run for even longer. Validation accuracy/loss does sit slightly below/above that of the training set, though, which suggests that the model is slightly overfitting to the training data—not unexpected given the small amount of data we have. The simple model utilises Batch Normalisation and Dropout, but these can only help so much.

The confusion matrix also gives us some interesting insight into what the model is doing. We can see that it tends to work very well on healthy leaves, but struggles somewhat with identifying diseased ones. This might be because of the shear variation in leaf types and their corresponding diseases, i.e. a healthy leaf is smooth and green, but a diseased leaf can be brown or yellow, with bumps or smooth, intact or torn.

### The pretrained model

{{< figure library="true" src="/plant_classification/pretrained/performance_over_time.png" style="width:48px;height:48px;" title="Model accuracy and loss over time, for the simple model, on the training and validation data." >}}

{{< figure library="true" src="/plant_classification/pretrained/confusion_matrix.png" style="width:48px;height:48px;" title="Confusion matrix for the simple model." >}}

Our pretrained model does at least as well as the simple model right out of the box, and its accuracy only increases with the minimal training we provide it. Validation measures remain close to the training ones, but again may indicate a slight overfitting that is increasing in time. This is a very powerful model, though, and in general, the more complex the model the faster it will overfit.

Regardless, the confusion matrix shows that this model is handling the data much better and more consistently. It doesn't get it right all the time, but tends to identify healthy and diseased leaves with roughly the same true/false-positive/negative rates.

### The takeaway

While the specific design of a model is important, at the end of the day the number and quality of the data is what really limits the accuracy of a CNN model. In some settings it will make sense to build a new CNN and train on a local dataset, but for most companies and most applications, it's much more efficient to use a pre-existing model and train the last few layers.
