# Stage D Tag - Along Code

# Neural Network, Image Recognition & Object Detection

The model built was done for submission as part of the requirements for Hamoye Data Science Internship stage D.

**DataSource:** This was also a submission for the [Kaggle - Planet: Understanding the Amazon from Space](https://www.kaggle.com/competitions/planet-understanding-the-amazon-from-space/submissions) competition.

**Description:** The competition was to build a model to recognize and tag images of the amazon from space. This was a supervised learning problem were a dataset of over 40,000 images were provided with a .csv file mapping image file names to the tags given to them. 

This multi-label problem was addressed using tensorflow keras framework to preprocess the images bringing them to size and building a model on top of the [MobileNetV2](https://tfhub.dev/google/imagenet/mobilenet_v2_100_224/feature_vector/4) as a base model (feature extractor layer).

Predicitions were then made on unlabeled test images and the tags given were saved in a .csv file and submitted. This submission got a public score of 0.79309 (on a scale of 0 - 1 with 1 being the maximum obtainable score).

![score](Score_Image.jpeg)

**Challenge Encountered:** 

Initially, I observed that the fbeta score was "flat" on the training data and "noisy" on the validation set although the loss curve was forming as expected indicating that learning was indeed taking place. This was a consistant occurence regardless of several attempts to tune hyperparameters and even change the optimization algorithm. On further investigation, I observed that the model was making the same predictions on all the input images.

Eventually, I observed that the tensors representing the images were arrays of zeros. Finally, I found out that this was due to the fact that the images weren't in the expected RGB encoding but rather in CMYK encoding. Where the K ("black channel") had zeros as its values.

It was clear from my research on this issue that the tensorflow "tf.io.decode_jpeg" method hadn't been optimized to handle 4-channel images of this nature and so my model wasn't performing as expected because of the fault in my image pre-processing.

**Solution:**

To fix this, I had to rebuild the input pipeline for my model in a manner were the image tensor isn't affected by the 4th channel which was creating the bug.

To do this, rather than using the "MultiLabelBinarizer" from sklearn for one-hot encoding of the labels, I had to "manually" create dummy columns and use the "ImageDataGenerator" module and "flow_from_dataframe" method to build my image input pipeline.

## Key areas tested in this quiz:

- Multi-label classification using neural networks.
- Convolutional neural networks.
- Transfer learning.
- Hyperparameter tuning in deep learning.
- Error analysis and debuggin of neural networks.