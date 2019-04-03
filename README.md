# cat-classification

### Introduction

This repository contain my final project for the Machine Learning Nanodegree on Udacity. The objective of this project is to train a CNN to take some picture and recognize which one of my two cats is in that picture.

The main challenge of it is that I have a total of 400 images for training, validation and testing, a small number to train CNNs. For that reason, I used transfer learning and data augmentation to get better results. I used three transfer learning models imported from Keras (NasNet Large, InceptionResNetv2 and Xception),

### Structure

In the main folder of this repository there are the 5 notebooks with all the code needed for the project, one pdf containing the proposal of the project ([Capstone Proposal](https://github.com/luiznonenmacher/cat-classification/blob/master/Capstone%20Proposal.pdf)) and another pdf ([Capstone Project](https://github.com/luiznonenmacher/cat-classification/blob/master/Capstone%20Project.pdf)) with a detailed explanation of the implementation and results of the project.

In the data folder there is all the data used in the project and the data generated after processing. One caveat is that because of github file limitation, the original data can be found on Google Drive in this [link](https://drive.google.com/drive/folders/1Vd1d-YemnPgA88VNZ9HR_CnsBNKFutAo?usp=sharing). The processed data folde is also empty because of size limitations, but the data can be obtained by running the Data Preprocessing notebook. Finally, the models folder contain the best models trained in the notebook as .hdf5 files.

Below are a quick overview of each notebook:

[1 - Image Preprocessing](https://github.com/luiznonenmacher/cat-classification/blob/master/1%20-%20Image%20Preprocessing.ipynb): The original images are imported, converted and saved to the desired output (299x299x3 and 331x331x3) for the transfer learning models.

[2 - Bottleneck Features](https://github.com/luiznonenmacher/cat-classification/blob/master/2%20-%20Bottleneck%20Features.ipynb): From the processed data obtained in the last notebook, I pass all the images trough the transfer learning models to obtain the bottleneck features used in the next steps.

[3 - Benchmark Model](https://github.com/luiznonenmacher/cat-classification/blob/master/3%20-%20Benchmark%20Model.ipynb): Before training the transfer learning models, I train a CNN from scratch and take its results as a benchmark for the transfer learning.

[4 - Transfer Learning](https://github.com/luiznonenmacher/cat-classification/blob/master/4%20-%20Transfer%20Learning.ipynb): I train three transfer learning models imported from Keras using the bottleneck features.

[5 - Data Augmentation](https://github.com/luiznonenmacher/cat-classification/blob/master/5%20-%20Data%20Augmentation.ipynb): To increase the performance of best model trained on the last step, I use data augmentation to generate new data to train a better model.

### Results

Usings a test dataset o 60 images (15% of the data), I was able to obtain an accuracy of 0.6170 training a CNN from scratch (Benchmark Model), an accuracy of 0.9167 using a pre-trained NasNet Large model followed by one-neuron layer and a final accuracy of 0.9500 using the same pre-trained NasNet model with two fully connected layers and using data augmentation to obtain more data.

### Requirements

This project was done using Python 3.7.1 and the following libraries and versions:

- numpy  1.16.2
- Keras  2.2.4
- Keras-Applications  1.0.7
- Keras-Preprocessing  1.0.9
- tensorflow  1.13.1
- scikit-learn  0.20.1
- pandas  0.23.4
- opencv-python  4.0.0.21
- matplotlib  3.0.2