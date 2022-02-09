# FTD_Project_3

This project is a continuation of FTD_Project_2. FTD_Project_2 can be viewed in the "Fintech_Submission_Branch" branch of this git repo. FTD_Project_2 aimed to discover whether or not FTD and Short Interest data could be used alongside machine learning in order to make predictions on a stocks future price movements, predictions which could then be used to make real trading decisions with.

The answer appeared to be yes, models can be made with FTD and Short Interest data - However, there are two main issues to overcome before the models could really be used to make real-life trading decisions. 


FTD_Project_3 aims to solve this problem, and eventually present a working, complete and tradeable model, by using additional machine learning techniques alongside our existing data to attempt to predict the missing FTD data for the final 15 days we do not have. 

Problem One : FTD data 
The FTD from the SEC, which is permanently delayed by 10 trading-days (2 weeks) or more, is the most significant issue, because it means the models would be missing the most recent data while attempting to make price predictions. 
To try and overcome this, we thought of two solutions:
Try predicting the missing FTD data using machine-learning techniques 
    This failed, for many reasons
Remove the FTD Data from the models, which would serve two purposes
    It outright solves the problem of the delayed data
    Provides a proper comparison and evaluation of the FTD Data and its effect on the accuracy of the models 
    
Problem Two : Improving Model Accuracy and Predication Capabilities
While the models from Project 2 were able to quite accurately track the same-day closing price using our provided dataset, they were not ready or set up to accurately make future predictions using the data. 
Originally, the models only really performed same-day predictions using our datasets
Now, the Neural Network (NN) models have been improved to be capable of 1, 2, 5 and 10-day forecasting 
Additionally, an LSTM-model has been created which can supplement the NN models as additional prediction method. 
    The LSTM model method is quite effective at predicting same-day prices, similar to the NN from Project_2, however it requires significant amounts of setup and time to run in order to accurately forecast prices as effectively as the NN models 

Model Details 
Five sets of models were created and trained
For the first three model sets: 
Data was used from the start of 2016 until the end of December 2021
Predictions were then made up to the first 10 trading days into January
This allowed the models to be accurately evaluated, as all data from January is available 
The last two model sets:
Use data up to the end of January 2022 
Proof-of-concept of how this project can be used to predict closing prices on stock symbols 

What is a model set? 
Model set = 770+ individual models, one (or 4) per stock symbol provided 
Models 1, 2, and 4 contain 4 models per symbol, or 3080 models per set 

What are the model sets?

Model_1 
Is a Neural Network which provides 1-, 2-, 5-, and 10-day price forecasts
Trained with FTD data  

Model_2 
Also a Neural Network which provides 1-, 2-, 5-, and 10-day price forecasts
Did not train with FTD data 
Used as a control to Model_1 to compare the effect of FTD data on the accuracy of our models 

Model_3
LSTM model which provides a 1-day price forecast 
Trained with FTD data 
Proof-of-concept of how to use machine learning methods which require 3-dimensional inputs with our dataset 
 
Model_4 
Is a Neural Network which provide 1-, 2-, 5-, and 10-day price forecasts
Includes data up to the end of January 2022, in order to provide a forecast into February 2022 
Trained without FTD data, as FTD data at the moment does not go to the end of January 

Model_5
An improved LSTM model relative to Model_3 
Attempts to provide a 10-day price forecast like the forecast provided by Model_4 






There are five folders with useful model data that will be used for the project presentation
All located in '../Model_Data/'

There are two sets of Neural Network (NN) models which are direct improvements upon the original machine-learning models from FTD_Project_2. The difference between each set, which should be obvious from the title path, is one set of models was trained with and including the SEC's FTD data, while the second set had the FTD data omitted from the models. Each model is improved relative to FTD_Project_2, because now they not only attempt to predict the close price with the data provided, but now they attempt to forecast the close price 1, 2, 5, or 10 days in advance. 

Model locations: 
Model_1: 
path_1 = Path('../Model_Data/Date_Test_NN_noFTD_all/')   Contains models trained without FTD data
Model_2: 
path_2 = Path('../Model_Data/Date_Test_NN_w_FTD_all/')   Contains models trained with FTD data 



The third set of models shares a similarity with the previous two NN models - it used the same dataset (up to Dec31st) to train, however, instead of a neural network (NN) model, it is an LSTM model designed to supplement the performance of the NN models and compare its results alongside. This third model does not predict/forecast data in quite the same way as the NN models - it should be used as a comparison or addition to the 1-day NN models listed above. It also acts as demonstration that LSTM-models can also be used, in addition to NN, to predict/track the closing price using our FTD, Short Interest, and Historical Pricing dataset. 

Model Location:
Model_3: 
path_3 = Path('../Model_Data/LSTM_Model_Data_1/')  ## Contains LSTM models trained with FTD data, up to Dec31st. 



The fourth set of models were designed after early evaluations of models _1 and _2. The purpose of the first two models was to compare the effect of removing the FTD Data from the features of the machine learning model, and early evaluations showed that, while definitely improving the accuracy of the models when included, the FTD data was not necessary or required in order to achieve accurate price tracking / predictions. So, the fourth (and fifth) models were designed as concept of how these models could genuinely be used to make predictions, select stock symbols, plan a buying strategy, and actually trade using these models that have been created over the course of this project. 

Model Location:
Model_4:
path_4 = Path('../Model_Data/Feb2022_NN_models/') Contains NN models, capable of taking January's data and making predictions 1, 2, 5, or 10 trading days into February. 
    
The fifth set of models were created for the same purpose as the fourth and perform a 10-day forecast of close price for a given stock. Instead of a NN model, this is an improved-upon (relative to Model_3) LSTM model that alongside our NN can be used to forecast stock price predictions, with enough accuracy that one could consider trading off these models. 

Model Location:
Model_5:
path_5 = Path('../Model_Data/Feb2022_LSTM_models_1/'






Code is located in their respective Functions_ Folder


## Machine Learning Folders

Model locations: 
Model_1: 
path_1 = Path('../Model_Data/Date_Test_NN_noFTD_all/')   Contains models trained without FTD data
Model_2: 
path_2 = Path('../Model_Data/Date_Test_NN_w_FTD_all/')   Contains models trained with FTD data 

Model Location:
Model_3: 
path_3 = Path('../Model_Data/LSTM_Model_Data_1/')  ## Contains LSTM models trained with FTD data, up to Dec31st. 

Model Location:
Model_4:
path_4 = Path('../Model_Data/Feb2022_NN_models/') Contains NN models, capable of taking January's data and making predictions 1, 2, 5, or 10 trading days into February. 

Model Location:
Model_5:
path_5 = Path('../Model_Data/Feb2022_LSTM_models_1/'


## Updates 

Models are finished. For now.  

## Next steps - 

Finish presentation and prepare front-end demonstration. 