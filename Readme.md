# Exploring 311 service request dataset

Here are the instructions and details about the notebooks and datasets.
The original dataset (311_service_requests) can be downloaded from NYC Open data (https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9)
Apart from the above, we are attaching an intermediary dataset (311_preprocessed_dataset) for reproducibility of our Data Analysis, Modelling and other notebooks.
We are also attaching holidays dataset from 2021 (holi_2021), 2022 (holi_2022) and 2023 (holi_2023) datasets for analysis on correlations of holidays with the complaint records.


Our project work is categorized in the following notebooks
1) 311_preprocessing.ipynb:
=> Contains all the preprocessing logic for the 311 dataset as well zip code dataset
2) 311_dataAnalysis.ipynb:
=> Contains the comprehensive data analysis for the 311 dataset along with zipcode dataset for visualization purposes
=> Also contains graphs and charts of various details
3) 311_modelling.ipynb:
=> Contains the Regression and Classification models used for our study
4) 311_holidaysDataAnalysis.ipynb:
=> Contains the holiday dataset analysis with the 311 dataset to understand the relationship of complaints with different holidays
5) 311_samplingValidation.ipynb:
=> Contains the script used for validation of agency distribution of 311 dataset.

We would prefer to execute the notebooks in the following order:
1) 311_preprocessing
2) 311_dataAnalysis
3) 311_holidaysDataAnalysis
4) 311_modelling
5) 311_samplingValidation
