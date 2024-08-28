Transfer Learning for Image Classification with Keras
-----------------------------------------------------

This code implements a transfer learning approach for image classification using Keras. Here's a breakdown of what it does:

**1\. Imports:**

-   Loads necessary libraries for building and training a CNN model.

**2\. Configuration:**

-   Defines image size (224x224) compatible with the pre-trained VGG16 model.
-   Specifies paths to training and validation datasets.

**3\. Pre-trained Model:**

-   Loads the VGG16 model pre-trained on ImageNet, excluding the top classification layers.
-   Freezes the pre-trained weights of VGG16 to focus on training new layers.

**4\. Model Building:**

-   Flattens the output of VGG16 from a 4D tensor to a 1D feature vector.
-   Adds a dense layer with the number of neurons equal to the number of classes.
-   Defines a Keras model with VGG16 as the feature extractor and the dense layer as the classifier.

**5\. Training:**

-   Compiles the model with categorical cross-entropy loss, Adam optimizer, and accuracy metric.
-   Creates data generators for training and validation sets using `ImageDataGenerator`:
    -   Rescales pixel values to the range [0, 1].
    -   Applies data augmentation techniques on training data (random shear, zoom, and horizontal flip) to increase robustness.
-   Trains the model using `fit_generator` on the training data with validation on the validation data.

**6\. Evaluation:**

-   Plots training and validation loss and accuracy curves to assess model performance.

**7\. Saving the Model:**

-   Saves the trained model for future use.

**Overall, this code demonstrates how to leverage a pre-trained model (VGG16) for feature extraction and build a new classifier on top for a specific image classification task.**
