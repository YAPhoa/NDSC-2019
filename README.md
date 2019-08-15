# NDSC-2019
This repository contains my approach for NDSC 2019. The competition task was to categorize items based on images and title to 53 classes. The competition metric was using accuracy <br> <br>
[Competition website](https://careers.shopee.sg/ndsc/)<br>
[Kaggle Competition Link](https://www.kaggle.com/c/ndsc-beginner/overview)

# Details
So in this competition I only use simple text preprocessing. The model itself is a simple stack of Bidirectional RNNs, using combination of both GRU and LSTM (to improve training speed significantly I used CuDNN version). Each models are trained individually for each big category (Fashion, Mobile, Beauty).<br><br>
To improve score and slightly reduce overfitting, I trained with 8-Fold stratified CV and average the inference from these models. Text preprocessing I used was removing extra blank spaces and standalone numbers (this is based on my observation that many of the title contain prices of the product and seller phone number which is not helpful for our task). 
Text embedding using FastText trained unsupervised with both train and test set.

# Score
Late submission 
public LB : 0.77316
private LB : 0.77468
