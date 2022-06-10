# csgo-round-win-predictor
A machine learning project on predicting the winner for a round in Counter-Strike: Global Offensive (CSGO).

# About This Project
This project aims to build and train a model that can predict the winner for a round of CSGO. The model uses in-game data such as a team's monetary value and number of players alive among others to predict the winner. The multiple models were trained, and the one that obtained the most accuracy on the onset was XGBoost. The model's hyperparameters were then tuned using Weights & Biases' sweeps. 

# Data Info
The merged and transformed data has a total of 132,828 samples and 107 features. The data was split using a stratified shuffle split that was stratified both on year the data was recorded (2019 for Kaggle, 2022 for Antwerp) and the round winner.

## Data Sources
This project uses data sourced from [Kaggle](https://www.kaggle.com/datasets/christianlillelund/csgo-round-winner-classification), PGL Antwerp 2022, PGL Stockholm 2021, and our own data. The Kaggle and Antwerp data were used to train the model, while our own data as well as the Stockholm data were used as a holdout dataset to test the model's generalizability. 

The Antwerp, Stockholm, and amateur data were parsed using the [AWPY module](https://github.com/pnxenopoulos/awpy). They were parsed using the [awpy_data_process.ipynb](../master/awpy_data_process.ipynb), which parses CSGO .dem files in the specified folder. This outputs .json files, which are then parsed and converted into a Pandas dataframe that fits the format of the Kaggle dataset. This is then transformed using the same pipeline that is used to transform the Kaggle data.

# Acknowledgements
This project would not have been as extensive without Xeno's [AWPY module](https://github.com/pnxenopoulos/awpy), which has been instrumental in being able to use non-Kaggle data. This module made it possible to use any CSGO .dem file we wanted, which allowed to use the Antwerp, Stockholm, and our custom data.

