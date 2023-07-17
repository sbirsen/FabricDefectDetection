# FabricDefectDetection
Classifying fabric images as defected or defect-free by using CNN model. 


1. Binary Classification Woven Without Augmentation [Defected Images: 71 images, Defect-Free Images: 71 Images]

In this code, a woven fabric dataset that contains defected and defect-free images is used to train and test a CNN model. 
The aim of the model is to classify images as defected and defect-free. 
The dataset contained 5 classess, and 4 of them are used to form defected sample images while 1 of them is used for forming defect-free samples. 
The class balance has been kept and controlled throughut the dataset preparation and train, test, validation split. 
In this case, no data augmentation technique is applied. 

After training and validating CNN, below performance is obtained with the test dataset. 
1/1 [==============================] - 0s 327ms/step - loss: 1.2713 - accuracy: 0.4000
[1.2712551355361938, 0.4000000059604645]

Confusion Matrix:
[[1 7]
 [2 5]]
Accuracy: 0.4
Recall: 0.7142857142857143
Precision: 0.4166666666666667
Specificity: 0.125
F1-score: 0.5263157894736842


2. Binary Classification Woven 1st Augmentation [Defected Images: 213 images, Defect-Free Images: 213 Images]

In this code, the main steps and the dataset that is used are kept as the same as previous code. However, the dataset is increased by the application of data augmentation. 
The augmentation is applied on robodlow website. 
Applied augmentation techniques were as below. 
  Outputs per training example: 3
  Flip: Horizontal, Vertical
  Rotation: Between -15° and +15°
  Shear: ±15° Horizontal, ±15° Vertical
  Saturation: Between -25% and +25%
  Noise: Up to 2% of pixels

In addition, some preprocessing steps are applied: Auto-Orient: Applied, Resize: Stretch to 416x416.

After training and validating CNN, below performance is obtained with the test dataset. 
2/2 [==============================] - 1s 681ms/step - loss: 1.0404 - accuracy: 0.4878
[1.0404382944107056, 0.4878048896789551]

Confusion Matrix:
[[12  8]
 [13  8]]
Accuracy: 0.4878048780487805
Recall: 0.38095238095238093
Precision: 0.5
Specificity: 0.6
F1-score: 0.4324324324324324

3. Binary Classification Woven 2nd Augmentation [Defected Images: 2982 images, Defect-Free Images: 2982 Images]

In this code, the main steps and the dataset that is used are kept as the same as previous code. 
However, a 2nd augmentation is applied by phyton in order to reach higher number of data. This augmentation is applied on top of the 1st augmentation set.
Applied augmentation techniques were as below. 
  Outputs per training example: 14
  Random brightness augmentation (0.7, 1.3)
  Random contrast augmentation (0.8, 1.2)

In addition, some preprocessing steps are applied: Auto-Orient: Applied, Resize: Stretch to 416x416.

After training and validating CNN, below performance is obtained with the test dataset. 
19/19 [==============================] - 3s 133ms/step - loss: 2.5597e-06 - accuracy: 1.0000
[2.559688937253668e-06, 1.0]

Confusion Matrix:
[[296   0]
 [  0 298]]
Accuracy: 1.0
Recall: 1.0
Precision: 1.0
Specificity: 1.0
F1-score: 1.0

