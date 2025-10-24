# Chest-CTscan-Image-Classification

**Data Source:** Chest CT-Scan images Dataset, Kaggle: https://www.kaggle.com/datasets/mohamedhanyyy/chest-ctscan-images

The transfer learning technology was used to build a model of convolutional neural networks for the purpose of classifying three types of cancer (Adenocarcinoma, Large cell carcinoma, Squamous cell carcinoma) on CT-Scan images.
The work consists of two parts:
* Building a CNN model with several convolutional layers and max-pooling layers.
* Building deep models with pre-trained weights on the ImageNet image set, namely: Xception, VGG16, ResNet50, InceptionV3, DenseNet121, ConvNeXtTiny, EfficientNetV2L.

During training, pre-trained weights were frozen for the models. After that, quality assessments were calculated for each of the models: loss value, accuracy, precision, recall, F1-score, AUC, training time, and graphs of changes in the loss function and accuracy index during training. The best model was selected based on the F1-score metric. Training was also performed for 10 epochs, with early stopping based on the loss quality indicator.

As a result, the best behavior was shown by the **DenseNet121** architecture, where:
* Validation Loss: 0.269829 | Test Loss: 0.594335
* Validation F1-score: 0.888889 | Test F1-score: 0.806349
* Validation Accuracy: 0.888889 | Test Accuracy: 0.806349
* Validation Precision: 0.888889 | Test Precision: 0.820598
* Validation Recall: 0.888889 | Test Recall: 0.784127
* Validation AUC: 0.987494 | Test Precision:0.945768
* Time (s): 550.7

The worst behavior was shown by the **EfficientNetV2L** architecture, where:
* Validation Loss: 1.283070| Test Loss: 1.486738
* Validation F1-score: 0.375000 | Test F1-score Loss: 0.438095
* Validation Accuracy: 0.375000 | Test Accuracy: 0.438095
* Validation Precision: 0.440678 | Test Precision: 0.463320
* Validation Recall: 0.361111 | Test Recall: 0.380952
* Validation AUC: 0.727366 | Test Precision:0.628432
* Time (s): 1760.9

In addition, the metrics of the models **InceptionV3, Xception** also had better results on both the validation and test sets.

While the metrics of the own convolutional network **cnn_model** are as follows:
* Early stopping after 13 epochs.
* Validation Loss: 0.704173
* Validation F1-score: 0.736111
* Validation Accuracy: 0.736111
* Validation Precision: 0.761905
* Validation Recall: 0.666667
* Validation AUC: 0.912166
* Time (s): 445.63

It can be seen that the best model makes the most errors for images of class "0", classifying them as "3". While the worst model did not classify the first two classes at all.
