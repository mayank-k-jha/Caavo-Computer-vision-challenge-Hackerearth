============================================================================

CAAVO COMPUTER VISION CHALLENGE (April 2018 - April 2018) (rank 29/2505)

============================================================================


--------------------------------------------------------------------------
Problem Description :->

A multiclass classification problem orgainsed by Hackerearth. Given dataset
contains total 62258 train images and 21273 test images of different types
of apparels divided into 15 categories. All images in training as well as
testing dataset are uniquely named. Challenge was to build a machine 
learning / deep learning model to classify given image into one of these 
categories.

Evaluation Metric : F1 Score with micro averaging (due to class imbalance)

--------------------------------------------------------------------------
EDA :->

As given dataset was set of images, so I proceed with visualizing class
distribution for each of apparels. Some of the classes I found was 
imbalanced and there were very less data as comapred to other classes.
(like 1:10 ratio). Another thing I observed that some of the classes
has very few images like in hundreds for training purpose which was
not a good indicator for training.
Another thing I observed was some images were too large in dimensions
as compared to their similar images, so we need to resize all of them
in same scale or aspect ratio. Most of the images were taken in good
lighting conditions while some were in bad lighting consitions. So, we
have to normalize it.
Most importantly, I found data leakage. I observed that the naming
conventions of images do have information that can tell us about their
target. But, to keep competition fair, I didn't use it. But others used
it just before half an hour when the competition ends due to which my
ranking suffers little bit.  


--------------------------------------------------------------------------
Preprocessing :->

Resize images to 100 * 100
Done normaliztion by scaling to 0-1 through division by 255 pixel value
Image Augmentation through keras ImageDataGenerator
(used: rescaling, rotation,width shift, height shift)


--------------------------------------------------------------------------
Modeling :->

After image augmentation,I started designing my own simple CNN architectures.

Architecture 1:
5 Layer deep architecture (4 CNN and one dense layer)
Used relu activation throught CNN and softmax for output layer.
Used filters 32->32->128->128 then 256 hidden units in dense layer.
Used dropout with 0.25
Accuracy : 0.30

Architecture 2:
5 Layer deep architecture (4 CNN and one dense layer)
Used relu activation throught CNN and softmax for output layer.
Used filters 32->32->64->64 then 512 hidden units in dense layer.
Used dropout with 0.3
Accuracy : 0.31 


Transfer Learning :

Architecture 3: 
VGG16
Used colored image.
Exclude top layer.
Accuracy : 0.45 (significant improvement of 15%)

Architecture 4: 
RESNET50
Used colored image.
Exclude top layer.
Accuracy : 0.47 (significant improvement of 2%)

Now it was time to use fine tuning. So, I fine tuned RESNET50 and thus
achieved around 48% accuracy on LB.

