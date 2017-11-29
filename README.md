# Bitcoin predict with CNN       

* Convolution Neural Networks for Bitcoin 

* Time series Binary classficiation prediction 

* Data from Korbit API 

![Alt text](https://www.bitcoin.com/wp-content/uploads/2017/06/usebitcoin-4096x2253.jpg)

# Introduction

Why CNN :

Different approach to time series problems. 

![Alt text](/Users/seyoungoh/Desktop/1.png)
  

What is about :

![Alt text](/Users/seyoungoh/Desktop/2.png)

Flow model :

![Alt text](/Users/seyoungoh/Desktop/3.pdf)

# Data

Data from Korbit API (Korean trasaction bitcoin history) 2016/06/28 to 2017/07/01

![Alt text](/Users/seyoungoh/Desktop/4.png)

Unlikely from research paper it was accumulated data.  Only used last, Volume columns.  

# Model

* Pre-processing
![Alt text](/Users/seyoungoh/Desktop/5.png)

* Scaling
![Alt text](/Users/seyoungoh/Desktop/6.png)
"last" & "volume" scaling max-min = 1
The graph save every 30 minutes in image file(png)

* First model
![Alt text](/Users/seyoungoh/Desktop/7.png)
Graph didn't seem to be meaningful

* Parameter
![Alt text](/Users/seyoungoh/Desktop/8.pdf)

* Second model
![Alt text](/Users/seyoungoh/Desktop/9.png)
After modified parameter (t+5) value will be greater than t.  
y=1 -> up   y=2 -> down

* Image process
![Alt text](/Users/seyoungoh/Desktop/10.png)       
![Alt text](/Users/seyoungoh/Desktop/11.png)    

* Model Graph
![Alt text](/Users/seyoungoh/Desktop/12.png)  
* first convolution (5.5 filters) 64
* second convolution (7.7 filter) 32
* max_pooling
* flattening
* second layer fully-connected
* sigmoid
* square_mean loss

# Test
![Alt text](/Users/seyoungoh/Desktop/13.png)  


# Tune
* batch_size
* total_epoches
* learning_rate
* optimizer
* hidden_dim
* learning_rate
* model structure
![Alt text](/Users/seyoungoh/Desktop/14.png)  
