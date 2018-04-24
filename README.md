# Caavo-Computer-vision-challenge
A multiclass classification problem orgainsed by Hackerearth.
Given dataset contains total 62258 train images and 21273 test images of different types of apparels divided into 15 categories. All images in training as well as testing dataset are uniquely named.
Challenge was to build a machine learning / deep learning model to classify given image into one of these categories.

# My Approach
As some classes have very few images so was better to reproduce some data in order to make our model more generalize and consistent. 
# 
So, I have used Image Augmentation to gerate some data for these classes. 
# 
Now after Image augmentation, now we have sufficient data to train a DeepNet. So, first I tried with making NN architectures from scratch and training it on whole data. Results was not so overwhelming. Had achieved around 30 % accuracy on LB.
# 
Now it was time to use transfer learning, So  first I used VGG16 due to its simple architecture complexity and achieved around 45% accuracy on LB. A significant improvement of over 15% in accuracy. With less resource capabilty, still used RESNET50 and INCEPTION V3.Through RESNET 50, accuracy was almost 46-47% using half of data than previous (Resource Problem :( ) but INCEPTION V3 was not working at all.
# 
Now it was time to use fine tuning. So, I fine tuned RESNET50 and thus achieved around 48% accuracy on LB.
That's it. :D

# Note :
Always follow No free Lunch Theorem. :)
