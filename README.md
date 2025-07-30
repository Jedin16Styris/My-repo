# Bitcoin Price Forecasting with Deep Learning 📈

This project showcases a deep learning model designed to forecast short-term Bitcoin (BTC) price movements. Using a **Long Short-Term Memory (LSTM)** neural network, the model analyzes historical price data to **predict the closing prices for the next 8 hours (32 intervals of 15 minutes)** and estimates the potential trading range.

The primary goal of this tool is to **reduce uncertainty for intraday traders** by providing a **data-driven forecast for the upcoming two 4-hour candles**, helping to prevent emotional decision-making and clarify potential market direction.

---

## 🚀 Key Features

- **🧠 Deep Learning Model**: Built using a **stacked LSTM network**, which is particularly effective for learning from time-series data.  
- **⏱️ Intraday Forecasting**: Predicts the **next two 4-hour candles (an 8-hour period)**, providing a valuable outlook for short-term trading strategies.  
- **📊 Trading Range Estimation**: Estimates an **approximate 8-hour trading range**, offering insights for **risk management and setting price targets**.  
- **📈 Rich Visualizations**: Interactive charts created with **Matplotlib & Plotly** to visualize model performance and forecasts against actual price data.  
- **🛠️ Tech Stack**: Developed in **Python** using leading data science and deep learning libraries, including **TensorFlow/Keras, Scikit-learn, Pandas, and Yahoo Finance (yfinance)**.  

---

## ⚙️ Methodology

The model's methodology is structured to handle the volatile nature of cryptocurrency markets effectively.

### **1. Data Collection & Preprocessing**
- **Dataset**: The model is trained on one month of historical **BTC-USD closing price data**, collected from Yahoo Finance at a 15-minute interval.  
- **Normalization**: Closing prices are normalized using **Scikit-learn's MinMaxScaler** to scale the data between 0 and 1, which helps the model learn effectively.  
- **Data Splitting**: The dataset is divided into **60% for training** and **40% for testing**, allowing for a robust evaluation of the model's performance on unseen data.  

### **2. Model Architecture & Hyperparameters**
The core of this project is a **Long Short-Term Memory (LSTM)** neural network built with **Keras**. The specific hyperparameters were carefully tuned to optimize performance.

- **Input Shape**: Sequences of the past 15 price points (`time_step=15`) are used to predict the next value.  
- **LSTM Layers**: Two stacked **LSTM layers**, each with 50 units and using the **ReLU activation function**.  
- **Regularization**: **Dropout layers** with a rate of 0.2 are included after each LSTM layer to prevent overfitting.  
- **Output Layer**: A **Dense layer** with a single neuron produces the final price prediction.  
- **Optimizer & Loss**: The model is compiled using the **Adam optimizer** with **Mean Squared Error (MSE)** as the loss function.  
- **Training Parameters**: The model is trained for a maximum of **100 epochs** with a **batch size of 32**.  
- **Early Stopping**: Implemented with `patience=10` to halt training when the validation loss stops improving, ensuring optimal convergence.  

---

## 📊 Results

The model's performance was evaluated using various metrics, with the **training R² score consistently ranging from 0.90–1.00**, indicating a strong fit to the data.

### **Visual Outputs**
- **Figure 1**: The training and validation loss curves converge effectively, demonstrating that the model learns patterns without significant overfitting.  
- **Figure 2**: The comparison chart shows that the model's predictions closely follow the actual price movements for both training and test sets.  
- **Figure 3**: This chart presents the model's **8-hour forecast** based on the most recent price data, offering a clear, forward-looking projection.  

---

## 🎯 Conclusion

This project successfully demonstrates the potential of using **LSTM models** to support **intraday Bitcoin trading**. By forecasting the next two 4-hour candles and estimating an 8-hour trading range, the algorithm provides a **valuable tool for traders** looking to make informed, data-driven decisions.

The key advantage of this model is its ability to **reduce confusion and emotional decision-making** that often arise from market volatility. By offering a reliable estimate of the upcoming trading range, it can help **mitigate panic during price fluctuations** and encourage a **more disciplined and systematic approach** to trading.  

While effective, the model's performance is constrained by **Bitcoin's inherent volatility** and the **limited one-month dataset**. For optimal results, these predictions should be **integrated with personal technical analysis and sound risk management strategies**.  

---

## 💻 How to Run

### **Open in Google Colab**  
No setup needed! Click below to run the project instantly in your browser with Google Colab:  

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Jedin16Styris/My-repo/blob/main/BTC_Project%20(1).ipynb)

## ⚠️ Disclaimer

The information and predictions generated by this algorithm are provided **for educational and research purposes only**.  
They **do not constitute financial advice**, investment recommendations, or trading signals.  

Cryptocurrency trading is highly volatile and involves **significant risk** of loss.  
Always perform your own analysis and apply **sound risk management** before making any trading or investment decisions.  

