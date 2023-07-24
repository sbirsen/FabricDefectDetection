# FabricDefectDetection
Classifying fabric images as defected or defect-free by using CNN model. 


1. Binary Classification Woven Without Augmentation [Defected Images: 71 images, Defect-Free Images: 71 Images]

In this code, a woven fabric dataset that contains defected and defect-free images is used to train and test a CNN model. 
The aim of the model is to classify images as defected and defect-free. 
The dataset contained 5 classess, and 4 of them (DelikVeKesikHatasi, KumasDokusundaYabanciCisim, İplikHatasi, YagLekesiVeRenkHatasi) are used to form defected sample images (HataVar) while 1 of them (HataYok) is used for forming defect-free samples. 
The class balance has been kept and controlled throughut the dataset preparation and train, test, validation split. 
In this section, no data augmentation technique is applied. 

After training and validating CNN, below performance is obtained with the test dataset. 
1/1 [==============================] - 4s 4s/step - loss: 2.0109 - accuracy: 0.5333
[2.0109336376190186, 0.5333333611488342]

Confusion Matrix:
[[6 2]
 [5 2]]
Accuracy: 0.5333333333333333
Recall: 0.2857142857142857
Precision: 0.5
Specificity: 0.75
F1-score: 0.36363636363636365


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
2/2 [==============================] - 5s 680ms/step - loss: 1.7917 - accuracy: 0.4634
[1.7917134761810303, 0.46341463923454285]

Confusion Matrix:
[[11  9]
 [13  8]]
Accuracy: 0.4634146341463415
Recall: 0.38095238095238093
Precision: 0.47058823529411764
Specificity: 0.55
F1-score: 0.42105263157894735

3. Binary Classification Woven 2nd Augmentation [Defected Images: 2982 images, Defect-Free Images: 2982 Images]

In this code, the main steps and the dataset that is used are kept as the same as previous code. 
However, a 2nd augmentation is applied by phyton in order to reach higher number of data. This augmentation is applied on top of the 1st augmentation set.
Applied augmentation techniques were as below. 
  Outputs per training example: 14
  Random brightness augmentation (0.7, 1.3)
  Random contrast augmentation (0.8, 1.2)

In addition, some preprocessing steps are applied: Auto-Orient: Applied, Resize: Stretch to 416x416.

After training and validating CNN, below performance is obtained with the test dataset. 
19/19 [==============================] - 101s 3s/step - loss: 7.6796e-06 - accuracy: 1.0000
[7.679565896978602e-06, 1.0]

Confusion Matrix:
[[296   0]
 [  0 298]]
Accuracy: 1.0
Recall: 1.0
Precision: 1.0
Specificity: 1.0
F1-score: 1.0

