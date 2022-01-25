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

Parts above are finished

05 sorts the equities at this point, and cuts down the current list of symbols from just under 6000, to ones with relevant FTD and short interest statistics. 

06 appends technical indicator data to the dataframes and exports the new data. 



Next steps - 

(technical indicator part needs to be added either now or after 05)

Sort the symbols. Calculate TI. Shift the data(?). Start running machine learning models. 
