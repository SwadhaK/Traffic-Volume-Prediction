## Traffic Volume Prediction Using Deep Learning Models 🚦📊
Traffic congestion is a major global issue, leading to longer travel times, increased pollution, economic losses, and safety risks. Traditional methods, such as
expanding road infrastructure and conventional navigation systems, struggle to accurately predict future traffic conditions, especially in data-sparse areas. To address 
this challenge, advanced predictive models are needed to analyze historical and real-time traffic data. This study aims to develop an LSTM-based model to forecast traffic
flow up to two hours in advance, providing a proactive solution for optimizing traffic management and reducing congestion.

### Dataset
This dataset provides a comprehensive view of traffic flow of Chicago city, capturing a variety of factors that influence it. It consists of 33,744 entries, 
meticulously recorded to reflect the dynamics of traffic volume. Each entry is an amalgamation of weather conditions, temporal factors, and traffic metrics.

### Approaches and Comparisons
#### 1️⃣ Statistical Approach
Statistical models analyze historical traffic patterns based on time intervals (daily, weekly, seasonal). These models are simple, fast, and cost-effective but struggle with handling multivariate dependencies.
  - ARIMA (Auto-Regressive Integrated Moving Average):A widely used statistical model for traffic forecasting.Assumes historical patterns will continue in the future.
    Effective for simple time-series analysis but limited in capturing complex traffic variations due to its univariate nature.
#### 2️⃣ Machine Learning Approach
Machine learning (ML) techniques leverage large datasets to improve predictive accuracy beyond statistical models by considering multiple influencing factors.
  - Random Forest: An ensemble learning method combining multiple decision trees. Considers factors like weather, time, road conditions, and holidays.
  - K-Nearest Neighbors (KNN): Uses feature similarity to forecast future traffic values.Effective for short-term predictions but computationally expensive for large datasets.While ML models perform well with structured data, they struggle with capturing temporal dependencies effectively, which is crucial for traffic forecasting.

#### 3️⃣ Deep Learning Approach
Deep learning (DL) models, particularly neural networks, outperform traditional ML and statistical methods by capturing both spatial and temporal dependencies in traffic data.
  - Convolutional Neural Networks (CNNs): Converts time-series data into a 2D representation (image-like matrix) to extract spatial-temporal patterns.Highly effective for congestion detection using road surveillance images.Not the first choice for time-series forecasting but has shown promising results in transportation studies.
  - Recurrent Neural Networks (RNNs) and Variants:  Designed for sequential data but suffer from the vanishing gradient problem, limiting long-term memory.
  - Long Short-Term Memory (LSTM): Overcomes RNN's vanishing gradient issue. Retains long-term dependencies, making it ideal for time-series traffic forecasting.Highly accurate but prone to overfitting with deep architectures.
  - Gated Recurrent Unit (GRU): A simplified LSTM variant with fewer parameters. Easier to train while achieving comparable accuracy.

The objective of this project is to develop a multi-step RNN using an LSTM model to predict traffic volume two hours ahead, based on six hours of historical data from the dataset.

### Test Result and Analysis
We conducted manual hyperparameter testing by experimenting with LSTM unit values and incorporating various layer types (Convolutional, Dense, GRU, and Bi-Directional) while adjusting batch sizes. Due to the lack of well-established LSTM architectures, we systematically tested different configurations:
 - Model 1: Varied LSTM units, layers, and Dense units.
 - Model 2: Bi-Directional LSTM, alongside three reference models from TensorFlow (Dense, Conv, LSTM).
Custom Models: MyLSTM_1 and MyLSTM_2, both outperforming reference models.
Our best model featured bidirectional LSTMs with two custom forward and backward layers, two dense layers (512 units each), and a single-unit output layer. It achieved superior performance with low variance over multiple training epochs.

 ![image](https://github.com/user-attachments/assets/462cff04-70ca-4543-9183-b9800f5a697e)

 ![image](https://github.com/user-attachments/assets/dad9485e-c1d3-49a0-9a2a-3260f4efe113)




