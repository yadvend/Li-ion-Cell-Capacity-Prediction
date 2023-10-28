# Li-ion-Cell-Capacity-Prediction
Project Title: Predicting Lithium-Ion Battery Capacity using LSTM

Dataset:

- The dataset used in this project contained historical battery performance data, including voltage, current, temperature and various other parameters

- Final dataset is prepared by combining 12 mini datasets containing total 2364 rows


Methodology:
     
1) Data Preprocessing

- The dataset was sorted on the basis of TimeStamp column to get a sequence
 
- Time-series data was organized into sequences suitable for LSTM model training
   
2) Feature Engineering
   
- Relevant features like Voltage, Current, Temperature were engineered to enhance the model's predictive capacity

- More features could be taken or several features could be accumulated for better result

- Feature scaling was also done using MinMaxscaler

3) Exploratory Data Analysis
   
- Capacity plot was plotted across the entire dataset

- Plot of Capacity against Current, Voltage and Temperature were plotted to observe changing nature

4) Splitting Dataset

- The dataset is splitted into 70 and 30 (70% for training and 30% for testing)

- Rows of datapoint less than 1655 were put into training set and other into testing set

5) Model Architecture
  
There are two layers in this model:
     
  a) LSTM layer:

- Number of Units: 50
- Activation Function: ReLU (Rectified Linear Unit)
- Input Shape: (number_of_time_steps, number_of_features_per_time_step)
              
b) Dense Layer(Output Layer):
    
 - Number of Units: 1

 
c) Input Layer: 
    
  - It is not explicitly mentioned, it is implied by the input_shape parameter of the LSTM layer, with a shape of (number_of_time_steps, number_of_features_per_time_step)


 6) Model Training
              
- Training data was prepared for a time series prediction task

- For each iteration, we are taking records of previous five rows.This creates a sequence of five consecutive data points as an input feature

- For each iteration, value in the fourth column (capacity) is used as target or output value. It suggests that we are trying to predict a single value based on the preceding five time stamps

- Optimizer used is adam, loss function is mean squared error and evaluation metrics is mean squared error

- Training parameters like epochs = 1000 and batch size is 10

 7) Model Performance 

- On plotting the Real Battery Capacity Vs Predicted Battery Capacity the predicted one almost overlapped the real one indicating the accuracy in prediction is good

- Mean squared error comes out to be 0.00440 which is impressive


8) Future Work
  
- More features could be added to train the model, moreover aggregated features could also be used for better results

- More Data Points can also be added for better training and prediction







