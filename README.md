# Skin-Cancer-Classifier

## ABSTRACT

Cancer is one of the most widespread diseases on the planet. Cancer exists in
different forms and also occurs at different parts of the human body. Cancer claims close to 5
million lives every year and a considerable portion of this includes the skin cancer cases. Cancer is
basically the abnormal growth in the cells of the human body which can be caused by physical,
chemical or biological carcinogens in a staged and a gradual process. Skin cancer basically means
an abnormality in the growth of skin cells which results in a tumorous growth of the skin cells. On
a whole, skin cancer can be classified into 4 major categories - Actinic Keratoses, Basal Cell
Carcinoma, Squamous cell carcinoma and Melanoma. Our project aims at creating a highly
accurate and a highly optimized version of the classifier of the different types of skin cancer by
using different types of Image Processing and Image Recognition techniques involving
segmentation and Convolutional Neural Networks. Another aspect of the project is to classify a
particular skin image into non-cancerous skin diseases.
DATASET: The dataset we will be using for this project is the HARVARD HAM10000 dataset.
https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/DBW86T
It is a dataset of image having 7 classes:
● Benign
● Actinic Keratosis
● Intraepithelial Carcinoma
● Boen’s Disease
● basal cell Carcinoma
● dermatofibroma
● Melanoma

## APPROACH

### IMAGE PREPROCESSING 

#### ADDING NOISE

We have created a function called Noisy which will add poisson,Gauss or
salt-and-pepper noise based on the parameters passed.every image is read using the
OpenCV library.A random noise from the three is added.

#### IMAGE RESTORATION

Median filter works the best from the three provided
noises.Therefore,we have median filtering in Image restoration.The Median Filter is a
non-linear digital filtering technique, often used to remove noise from an image
or signal. Such noise reduction is a typical pre-processing step to improve the
results of later processing (for example, edge detection on an image

#### IMAGE ENHANCEMENT

It has been done using histogram equalisation. Histogram equalization is a technique
for adjusting image intensities to enhance contrast. Let f be a given image represented
as a mr by mc matrix of integer pixel intensities ranging. from 0 to L − 1. L is the number
of possible intensity values, often 256.

#### IMAGE SEGMENTATION

We have used thresholding segmentation .the dataset contains images having distinct tumor
regions and background skin. Therefore,thresholding segmentation by setting the mean of the
entire image as the threshold will work in this case.

### DATA PREPROCESSING

Libraries used are OpenCV, matplotlib,sys,Pandas,os,glob,numpy,random
The images extracted were in two different folders : Part 1 and Part2.
In order to get the image path,we have used the glob library and created a
dictionary having image name as the key and path as the value. Then,the
Pandas library is used to read the metadata.After that,the dictionary is
mapped to the Pandas dataframe and a new column of image_path is
added to the df.Now the image is read by the use of OpenCv library and
each individual image is resized to 100x100.Image is read in grayscale.The
image and the label is stored as a set of list ([image,label]).Now the entire
list is shuffled using the random shuffle function.The features and labels
are then separated into 2 different lists, X and y.

### ARCHITECTURE

Layer        No of units         Kernel Size
Conv1            32                  3x3
MaxPooling1      32                  2x2
Conv2            64                  3x3
MaxPooling2      64                  2x2
Conv3            128                 3x3
MaxPooling3      128                 2x2
FullyConnected   128                 N/A
Softmax          7                   N/A

###RESULT
We have created a model which will add noise, remove noise, enhance the
image, extract the important features from the image and will then feed it to
the neural network for the purpose of classification. We could conclude that
depending upon the training/validation split and the accuracy of the project
was around the 68% mark. In the paper, “Superior skin cancer
classification by the combination of human and artificial intelligence”
have mentioned their accuracy by the combination of human effort and
machine to be 82.95%. The highest accuracy achieved by a CNN model in
this data set is 81.59% and that by Human Intelligence is about 42.94%.
