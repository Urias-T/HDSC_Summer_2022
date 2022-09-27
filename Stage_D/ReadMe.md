# Stage D Tag - Along Code

# Neural Network, Image Recognition & Object Detection

The model built was done for submission as part of the requirements for Hamoye Data Science Internship stage D.

**DataSource:** This was also a submission for the [Kaggle - Planet: Understanding the Amazon from Space](https://www.kaggle.com/competitions/planet-understanding-the-amazon-from-space/submissions) competition.

**Description:** The competition was to build a model to recognize and tag images of the amazon from space. This was a supervised learning problem were a dataset of over 40,000 images were provided with a .csv file mapping image file names to the tags given to them. 

This multi-label problem was addressed using tensorflow keras framework to preprocess the images bringing them to size and building a model on top of the [MobileNetV2](https://tfhub.dev/google/imagenet/mobilenet_v2_100_224/feature_vector/4) as a base model (feature extractor layer).

Predicitions were then made on unlabeled test images and the tags given were saved in a .csv file and submitted. This submission got a public score of 0.79309 (on a scale of 0 - 1 with 1 being the maximum obtainable score).

![score](Score_Image.jpeg)

## Key areas tested in this quiz:

- Multi-label classification using neural networks.
- Convolutional neural networks.
- Transfer learning.
- Hyperparameter tuning in deep learning.