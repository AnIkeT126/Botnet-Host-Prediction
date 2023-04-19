# Botnet-Host-Prediction

Flow based analysis of network traffic from hosts in a live station modelled using GRU-RNN to classify botnets amongst those hosts.

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
         
         
         <li>Loss function: mean squared loss</li>
         
         
         <li> Activation Function: tanh, is applied on all the hidden layers. </li>
         
         
         <li> Optimizer: Stochastic Gradient Descent </li>
         
         
         <li> Train each IP from the model build to check the accuracy of the prediction. </li>
         
         
</ul>


10. Plot of the prediction for each IP i.e., each host against the actual flow is rigorous and not so clear.


11. The data is evolving in time and hence the use of Approximate Entropy values helps to evaluate time series entropies.


12. The entropy plots depict the idea that the hosts’ capturing more randomness are botnets as the flow is disrupted.


13. Classification of hosts can be done by calculating the mean of the total flow and prescribing a range where any mean lying outside the given range is a botnet host.
