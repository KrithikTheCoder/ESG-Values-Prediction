# ESG Forecasting Model: EMD-LSTM Framework

This project implements a forecasting model for Environmental, Social, and Governance (ESG) values across multiple countries using an Empirical Mode Decomposition (EMD) and Long Short-Term Memory (LSTM) hybrid approach. The methodology is outlined as follows:

## Methodology

1. **Data Preprocessing**: 
   - ESG time series data is decomposed into distinct Intrinsic Mode Functions (IMFs) using EMD to capture multi-scale patterns.
   - Each IMF is divided into training (60%) and validation (40%) sets and transformed into a windowed dataset (window size = 5) for model input, ensuring temporal dependencies are maintained.

2. **Model Architecture and Training**:
   - Individual LSTM models are trained on each IMF to capture unique temporal dynamics.
   - Architecture includes a 1D convolutional layer, multiple bidirectional LSTM layers with dropout for regularization, and a dense output layer for ESG value predictions.
   - Training is conducted for 500 epochs with the Mean Absolute Error (MAE) as the loss function, optimized using the Adam optimizer (learning rate = 0.001).

3. **Evaluation and Forecasting**:
   - Model performance is evaluated on a validation set, yielding an MAE of 2.36.
   - Forecasts for ESG values are generated over a 99-day horizon by applying the trained models to the decomposed IMFs, capturing country-specific trends.

4. **Results**:
   - The cumulative training loss across all models resulted in a final MAE of 0.82, indicating strong model accuracy in capturing ESG patterns.

This EMD-LSTM model effectively utilizes decomposition and sequential modeling to enhance ESG value forecasting, providing a comprehensive view of temporal dynamics across countries.
