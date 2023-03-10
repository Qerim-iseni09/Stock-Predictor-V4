# Stock-Predictor-V4

![stockpredictor ai logo](https://user-images.githubusercontent.com/53996451/224323224-3ec1cd20-747c-42ad-9fb1-ba6e0ecb358b.png)

Please note that this is still in the testing phase, so if you encounter any errors, please report them.

## 1a. Installation
```
git clone https://github.com/Qerim-iseni09/Stock-Predictor-V4.git
cd Stock-Predictor-V4
./install.sh # Ignore the 2 Messages
```

## 1b. Installation with Virtual Environment (venv) in Python
```
git clone https://github.com/Qerim-iseni09/Stock-Predictor-V4.git
pip install venv
python -m venv Stock-Predictor-V4
cd Stock-Predictor-V4
source bin/activate # Execute before using any script
./install.sh # Ignore the 2 Messages
deactivate # Execute this command to deactivate the virtual environment
```

## 2. Data Preparation
To prepare the data for your stock prediction, follow these steps:

1. Go to [Yahoo Finance](https://finance.yahoo.com/) and select a stock of your choice.
2. Download the CSV file from the Historical Data tab and save it in the data folder. For example, you can use [Bitcoin](https://finance.yahoo.com/quote/BTC-USD?p=BTC-USD) as an example.
3. Open `prepare_data.py` and change `df = pd.read_csv('data/BTC-USD.csv')` to `df = pd.read_csv('data/<Your Downloaded CSV file>')`, where `<Your Downloaded CSV file>` is the name of the CSV file you downloaded in step 2.
4. Execute `prepare_data.py` by running `python prepare_data.py`.
  
After these steps, your downloaded stock data will have indicators that make predictions more reliable.


## 3. Training the LSTM RL Model

To train the LSTM RL Model with the `data.csv` file that was generated by the 2. Step, execute the following:

```
python train.py
```
After running this command, the LSTM RL model will start training with the data in the data.csv file.


## 4. Evaluating the Model
To evaluate the trained model, execute the following:

```
python eval.py
```

After running this command, the accuracy, rewards, mean squared error (MSE), and root mean squared error (RMSE) will be plotted.


## 5. Fine Tuning the LSTM RL Model

Fine tuning the LSTM RL model will take more time as it will train until it reaches a specific accuracy threshold. By default, the accuracy threshold is set to 89.5%. However, if you want to set a different accuracy threshold, open the fine_tune.py file and change the accuracy_threshold variable to your desired target accuracy.

To fine tune the model, execute the following:
```
python fine_tune.py
```

This process will take some time, and it is recommended to hydrate yourself with some water while waiting for the fine-tuning to complete.
After fine-tuning is complete, it is recommended to re-evaluate the model.


## 6. Utilizing the Model for Stock Market Prediction
After completing the previous steps, you can use the model to predict the stock market for as many days as you want. The script will prompt you to enter the number of days to predict, and after plotting the predictions, it will ask you to rate the predictions on a scale of 1 to 10. The model will receive a reward based on your rating, which will help it improve its future predictions.

To use the model for prediction, run the following command:

```
python predict.py
```

And Happy Trading!
However, please note that any losses incurred by utilizing the model's predictions are not the responsibility of the developer.
