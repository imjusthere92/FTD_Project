# Fintech_Project_2

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



07 will run the Machine Learning models. 

07_01 will run non-shifted data for ML models
07_02 will run shifted data for ML models 

06_01 is finished. 06_02 still needs to be done. 
Starting 07_01 now and running ML models with no shifted data for now. 

Next steps - 

Shift data for TI, run models with shifted data. 

Then, compare and evaluate models, and go from there. 
