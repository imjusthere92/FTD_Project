# FTD_Project_3

This project is a continuation of FTD_Project_2. FTD_Project_2 aimed to discover whether or not FTD and Short Interest data could be used alongside machine learning in order to make predictions on a stocks future price movements, predictions which could then be used to make real trading decisions with.

The answer appeared to be yes, models can be made with FTD and Short Interest data - but with one significant problem: The FTD data from the SEC, is permanently delayed by 15 days or more, as the data is always released on a roughly two-week delay relative to when the actual data is recorded. 

FTD_Project_3 aims to solve this problem, and eventually present a working, complete and tradeable model, by using additional machine learning techniques alongside our existing data to attempt to predict the missing FTD data for the final 15 days we do not have. 

By using our models and data from FTD_Project_2, we can identify the most accurate models and stock symbols using our current data. And then supplement those models with LSTM models that attempt to predict FTD data for the missing 15 days. 

Afterwards, the models FTD_Project_2 can be used with the new column of predicted FTD data, alongside real, up to date EOD-data that was not present for training, in order to attempt to predict future price movements of our selected stocks. 

Additionally - control models (models without FTD data) will be created and evaluated to determine the exact effect FTD data is having on this Machine Learning Project, in comparison to the short interest data, techinical indicator data, and raw historical data also being fed into the models. 

At the moment - FTD data is available up to the end of 2021 (Dec 31st). On February 1st, FTD data for Jan 1st until Jan 15th will be released. These 15 days of FTD data will be compared against the FTD_LSTM models, to see if they are capable of accurately predicting FTD data ahead of when FTD released. 

If the data is accurate? Then we can use the predicted FTD data to fill in 15 day-delay in reporting, and then predict the following (Jan 16th-Jan 31st) price movements, and compare them to real-life data. 

If this works? Then this model can be used to make price predictions, every 15 days (on the 1st and ~15th of every month) to attempt to predict the next 15 days of trading movements. And these predictions can then be used to make trading decisions on the stock symbols that come out of this. 

If time allows - more than LSTM will be used for FTD prediction. But for now, a LSTM model will be contructed to suplement the existing neural network models that are accurately tracking price movement of approximately ~250 different stock symbols. 





Code is located in Functions_Jan2022 Folder

01 file is for gathering SEC data and combining it all together. 
01 exports ftd_all_data and symbol_all_list in Resources folder. 

02 file is for gathering historical EOD price data for the last 5-6 years, and combining it together with FTD statistics from and Short Interest Data from FINRA. 
02 exports dataframes, and the 02_symbol_success_list. Not all symbols in this list will be viable for Machine Learning, and further data needs to be gathered before settling on the symbols for the models. 

The folder for the raw historical data (at this point) is not on GIT, more data will be added before uploading the dataframes to git will occur. 

A successful symbol means the dataframe exported had >1500 rows of data in the dataframe, or ~6 years worth of historical data for Machine Learning. 

03 file is for gathering fundamental data about the successful symbols, and creating dictionaries for each stock symbol to be saved and read in other files.
03 exports data_dicts which contain fundamental data about each stock symbol, with the dataframe appended, all in one dictionary. 

See 'data_dict_structure.txt' for preview of how this data_dict is built, and can be accessed.      ## NOTE: Will need to update this text document with updated structure. 

04 performs calculations using the gathered data, in order to begin sorting symbols by their FTD quantities and short interest metrics. 
04 exports completed data_dict's, minus the technical indicator data, which still needs to be added and calculated. 


05 sorts the equities at this point, and cuts down the current list of symbols from just under 6000, to ones with relevant FTD and short interest statistics. 
05 contains calculations to determine outliers, maximums, and to perform specific calculations using current data

05 eventually sorts the 5493 symbols down to 1563 symbols, based off symbols which have both 5% of their outstandingShares/Float fail to deliver in the past year, while ALSO having 20% of total volume in same time period recorded as short sales

05 exports these symbols as 05_machine_learning_dict.pkl to be used in 06

## The 05_machine_learning_dict.pkl contatins the list of stocks that will be used for the ML models. 

06 appends technical indicator data to the dataframes, shifts the data, and exports the new dataframes, ready to be used for Machine Learning. 

06_01 appends TI calculations, without shifting the data
06_02 appends TI calculations, and also shifts the data 

## 07 will run the Machine Learning models. 

07_01 will run non-shifted data for ML models
07_02 will run shifted data for ML models 

## Machine Learning Folders
Model_Data_low_loss - contains Model Data for non-shifted data, FTD data and all 
      Resouces/symbol_accuracy_dict_low.pkl contains symbol keys and accuracy data for imports and evaluation. 
      
Model_Data_shift_low_loss - contains Model Data for shifted data, FTD data and all 
      Resouces/shift_symbol_accuracy_dict_low.pkl contains symbol keys and accuracy data for imports and evaluation. 

Model_Data_low_loss_2 - contains Model Data for same non-shifted data, but without FTD included
      Resouces_2/symbol_accuracy_dict_low.pkl contains symbol keys and accuracy data for imports and evaluation.


## Updates 

Machine learning models for 07_01(no shift), 07_02(shifted), and models with no FTD data are now finished.  

LSTM Models are complining and can now be tweaked and worked on. So far, they are terrible at predicting closing price, but results will hopefully be different for FTDs. 
Will compile both price prediction and FTD models overnight with basic LSTM settings before attempting to tweak LSTM arguments to improve models. 

## Next steps - 

Build LSTM models and other models and begin running variations of them. 

Evaluate existing models as they finish and begin determing the best results. 

Begin visualizing data and preparing for presentation. 