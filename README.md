# Botnet-Host-Prediction

### Flow based analysis of network traffic from hosts in a live station modelled using GRU-RNN to classify botnets amongst those hosts.

## Algorithm

1. Take the raw data as input.


2. The data consists of several logs from multiple days where each day has multiple logs whose features are date, IP i.e., IP corresponding a particular host, an Autonomous System Number (ASN) and the flow for the particular host.


3. Numbering the IPs form 0-n for different hosts depicting Local Flow i.e., count of connections helps in Grouping the data by date to analyze the total flow of the day.


4. The flow can be plotted against the day of the week.


5. The flow is also plotted against the day of the year.


6. The plot of the flow with respect to the day of the year for individual hosts using their IP helps in understanding the anomalies in the flow (if any).


7. The main task is to then create the sub dataset form the raw data by tagging the features and targets amongst the values available.


8. The model is then trained using GRU-RNN with the following specifications:
         <ul>
         
         
         Loss function: mean squared loss
         
         
         Activation Function: tanh, is applied on all the hidden layers. 
         
         
         Optimizer: Stochastic Gradient Descent
         
         
         Train each IP from the model build to check the accuracy of the prediction.
         
         
</ul>


10. Plot of the prediction for each IP i.e., each host against the actual flow is rigorous and not so clear.


11. The data is evolving in time and hence the use of Approximate Entropy values helps to evaluate time series entropies.


12. The entropy plots depict the idea that the hosts’ capturing more randomness are botnets as the flow is disrupted.


13. Classification of hosts can be done by calculating the mean of the total flow and prescribing a range where any mean lying outside the given range is a botnet host.


## Data Preprocessing

![Fig  2](https://user-images.githubusercontent.com/82095877/232967141-97ecf077-7792-474b-b414-d63537cfc3fe.png)
![Fig  3](https://user-images.githubusercontent.com/82095877/232967168-1e2ca825-f8fd-4c98-8ab5-8b7654cfbffb.png)
![Fig  4](https://user-images.githubusercontent.com/82095877/232967187-a5e197bd-ace3-48ab-b84e-fc8e2aaaf36b.png)
![Fig  5](https://user-images.githubusercontent.com/82095877/232967196-276ba1b5-3203-4fee-8a15-96c64296c4dd.png)
![Fig  6](https://user-images.githubusercontent.com/82095877/232967211-fb400813-72bd-48d1-808a-704eab3be97c.png)
![Fig  7](https://user-images.githubusercontent.com/82095877/232967218-d5240dda-f4cb-4b86-a817-566522aa49a5.png)

## Mean Range Modulation

![image](https://user-images.githubusercontent.com/82095877/232967333-40301533-c1bd-4f8f-b81c-69e1f81dcdeb.png)

## Accuracy Score

![image](https://user-images.githubusercontent.com/82095877/232967377-3c84f95b-cedd-41b0-8011-aa9dc4fde41b.png)


