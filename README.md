# Self-Driving Car Engineer Nanodegree
# Deep Learning
## Project: Build a Traffic Sign Recognition Program

### Overview

In this project, you will use what you've learned about deep neural networks and convolutional neural networks to classify traffic signs. You will train a model so it can decode traffic signs from natural images by using the [German Traffic Sign Dataset](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset). After the model is trained, you will then test your model program on new images of traffic signs you find on the web, or, if you're feeling adventurous pictures of traffic signs you find locally!

### Dependencies

This project requires **Python 3.5** and the following Python libraries installed:

- [Jupyter](http://jupyter.org/)
- [NumPy](http://www.numpy.org/)
- [SciPy](https://www.scipy.org/)
- [scikit-learn](http://scikit-learn.org/)
- [TensorFlow](http://tensorflow.org)
- [Matplotlib](http://matplotlib.org/)
- [Pandas](http://pandas.pydata.org/) (Optional)

Run this command at the terminal prompt to install [OpenCV](http://opencv.org/). Useful for image processing:

- `conda install -c https://conda.anaconda.org/menpo opencv3`

### Dataset

1. [Download the dataset](https://d17h27t6h515a5.cloudfront.net/topher/2016/November/581faac4_traffic-signs-data/traffic-signs-data.zip). This is a pickled dataset in which we've already resized the images to 32x32.
2. Clone the project and start the notebook.
```
git clone https://github.com/udacity/CarND-Traffic-Signs
cd CarND-Traffic-Signs
jupyter notebook Traffic_Signs_Recognition.ipynb
```
3. Follow the instructions in the `Traffic_Signs_Recognition.ipynb` notebook.

#**Test Results**
Follow the keras version `traffic-sign-classification-with-keras.ipynb` for updated results
###Validation accuracy 99.31 %
###Test accuracy 95.44 %


#Model architecture

convolution2d_11 (Convolution2D) (None, 28, 28, 6)     456         convolution2d_input_9[0][0]      
____________________________________________________________________________________________________
maxpooling2d_10 (MaxPooling2D)   (None, 14, 14, 6)     0           convolution2d_11[0][0]           
____________________________________________________________________________________________________
activation_10 (Activation)       (None, 14, 14, 6)     0           maxpooling2d_10[0][0]            
____________________________________________________________________________________________________
convolution2d_12 (Convolution2D) (None, 10, 10, 16)    2416        activation_10[0][0]              
____________________________________________________________________________________________________
maxpooling2d_11 (MaxPooling2D)   (None, 5, 5, 16)      0           convolution2d_12[0][0]           
____________________________________________________________________________________________________
activation_11 (Activation)       (None, 5, 5, 16)      0           maxpooling2d_11[0][0]            
____________________________________________________________________________________________________
flatten_7 (Flatten)              (None, 400)           0           activation_11[0][0]              
____________________________________________________________________________________________________
dense_15 (Dense)                 (None, 128)           51328       flatten_7[0][0]                  
____________________________________________________________________________________________________
dropout_11 (Dropout)             (None, 128)           0           dense_15[0][0]                   
____________________________________________________________________________________________________
activation_12 (Activation)       (None, 128)           0           dropout_11[0][0]                 
____________________________________________________________________________________________________
dense_16 (Dense)                 (None, 43)            5547        activation_12[0][0]              

Total params: 59747
____________________________________________________________________________________________________
Train on 26270 samples, validate on 12939 samples
