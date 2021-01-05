# Bloodcell_Subtype_Classification
Classifying subtypes of blood cell within images using three different Convolutional Neural Networks (CNN): a custom built CNN with 5 Conv blocks (1) and transfer learning using a fine tuned Densenet201 model (2) and a VGG16 model (3)

# Dataset: 
410 original images which have been augmented to form a dataset of 12,500. For more details on the augmentation process please read the ["Blood Cell Images" Kaggle Data page](https://www.kaggle.com/paultimothymooney/blood-cells)

# Loading Data:
On my first few attempts the Train and Test folders were used to create Training (and Validation) and Test datasets respective. However, following persistent overfitting of my models and feedback from users on other Kaggle notebooks suggesting poor data shuffling, I decided to combine the Train/Test folders and recreate the dataset using my own shuffling and splits (80%, 10%, 10%). 

# Results:

Model 1 (Custom built 5 block CNN):
![Confusion Matrix](https://github.com/NoBetterThanNoise/Bloodcell_Subtype_Classification/blob/master/confusion_matrix_model1.png)
Classification of Lymphocytes and Monocytes are near perfect with F1 scores of 0.99 and 1.00. The model also performs well at classifying Neutrophil and Eosinophil, however the two are occassionally confused especially when identifying Neutrophils. These are reflected in their F1 scores of 0.89

Model 2 (Densenet201): 
![Confusion Matrix](https://github.com/NoBetterThanNoise/Bloodcell_Subtype_Classification/blob/master/confusion_matrix_model3.png)
This Densenet Model shows similar patterns in test results that we saw in Model 1 (created in Part 1). Classification of Lymphocytes and Monocytes are very good with an F1 scores of 0.97 although not as good as in Model 1 (0.98 F1 score), while Neutrophils and Eosinophils and still confused on occasion with each other but fare slightly better than in Model 1.

Model 3 (VGG16): 
![Confusion Matrix](https://github.com/NoBetterThanNoise/Bloodcell_Subtype_Classification/blob/master/confusion_matrix_model3.png)
My VGG16 model (82.56%) performed significantly worse than the CNN built from scratch (94.05%) and the Densenet201 model (89.07%). Again we see the same trends of high performance on Lympocytes and Monocytes while struggling to classify Neutrophils and Eosinophils.

# Future work: 
- Explore Transfer Learning with other models such as InceptionV3 and Resnet18
- Create a VGG16/Densenet201 models with training enabled on the final Conv block.
- Explore optimization techniques and explore changes to hyperparameters (Learning rate, batch size, number of epochs etcs)

# References:
Some code was adapted from [Carlos Zuluaga](https://medium.com/@carlosz22/transfer-learning-using-keras-with-densenet-169-91679300f94a), [Vincee](https://www.kaggle.com/vincee/intel-image-classification-cnn-keras) and [Abhinav Sagar](https://towardsdatascience.com/deep-learning-for-detecting-pneumonia-from-x-ray-images-fc9a3d9fdba8)
