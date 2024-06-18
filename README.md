# lung_tumor_segmentation_capstone
This jupyter notebook is my solution for the Capstone Project of Udemy's Deep Learning with PyTorch for Medical Image Analysis course (https://www.udemy.com/course/deep-learning-with-pytorch-for-medical-image-analysis)


# Problem:
Segmentation of Lung Tumor on the CT scans of patients.

# Data:
Medical Segmentation Decathlon (http://medicaldecathlon.com/)
63 3D CT Scan files of the Lung were used for training with a 0.2 validation split. Due to the small number of slices containing tumor, oversampling was performed. Considering all individual slices of the 3D scans, a total number of 27729 train images and 2050 val images were used. 

# Augmentation: 
translate augmentation: 15 percent <br>
scaling: 0.85 to 1.15 <br>
rotation: -45 to 45 <br><br>

# Model:
A UNet (Depth:3) convolutional model was trained using Adam optimizer with 1e-4 learning rate and “BCEWithLogitsLoss” loss function. Total number of epochs was 30.  Training was performed on a cloud server with 60 GB of RAM and Nvidia GeForce RTX 3090 GPU. Training time was 3:30 hours. Test set contained 32 Scans.

# Results:
The Val Dice Score is: 0.36665797233581543 <br>
The IoU (Jaccard Index)  is: 0.22448328137397766 <br><br>

In case of threshold = 0.5: <br>
The precision  is: 0.816866863719263<br>
The recall  is: 0.23519718972947526<br>
The f1 score  is: 0.3652340180240978<br><br>

Highest sensitivity and ROC was obtained with threshold value of 0.1 and in this case: <br>
The precision  is: 0.6760949619995299 <br>
The recall  is: 0.3906221707166914 <br>
The f1 score  is: 0.495159726167318 <br><br>
 

Train set lung_003.nii.gz slice 140: <br>
 

Test set lung_085.nii.gz slice 187: <br>

