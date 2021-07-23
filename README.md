# ASL-Classification

## Overview
Currently there is no service available to the deaf that allows for easy communication between ASL and non ASL speakers. The primary goal of this project was to create a model that would be able to classify various images of the ASL alphabet and figure out correctly what English alphabets they correspond to. This is the first step towards building out a sign language interpreter that would be able to take pre recorded video of signing and provide an english translation. Sign language data was publicly available and was found on https://www.kaggle.com/datamunge/sign-language-mnist.

## Technologies Used
UNIX, Python, Pandas, Numpy, Matplotlib, Seaborn, Scipy, Sklearn, Tensorflow, Keras

## The Data
The data consists of 27,455 training cases and 7172 test cases. Each case consists of a label 0-25 that serves as a one to one map of the english alphabet. The training data consists of 27,455 rows and 784 columns as each image is 28x28 pixels so each column represents a single pixel value. In terms of preprocessing I normalized the data, checked for any imbalance amongst cases in the set, and added variations to randomly selected images by zooming slightly, or rotating slightly to reduce the possibility of overfitting.

Distribution of Classes Representing Each Alphabet:


## Analysis
The most successful model that i used was the CNN model. I developed the model by implementing the pattern of convolution, rectified linear unit, and then max pooling. At the end  I applied the flattening and softmax functionality to get the class probabilities. I ended up training with 20 epochs after seeing a plateau in the accuracy but realized that with further training the model had the potential to become even more accurate. Ultimately I ended up with a classification accuracy of 98.62%. I also implemented a Random Forest model initially but did not experience the same success as I ended up with a classification accuracy of 79.78%. I also generated a classification report for the CNN and found that class 4, class 6, and class 12 were not being predicted with maximum accuracy in terms of precision, recall, and f1-score. In conclusion I was able to create a successfull classifier and this is only the first step towards being able to classify in real time.

## Conclusion and Next Steps
This image classifier is the first step towards creating a tool that Non-ASL speakers can use to simply record ASL being performed and in real time get a live english translation. That is my ultimate goal for this project. I plan on testing the classifier on my own images that I created. I then plan to work with prerecorded video and use OpenCV to track the movement of each hand in a bounding box. Finally I want to be able to process all that data in real time. I think that this would prove to be a very helpful tool as there is currently nothing like it on the market today. 

