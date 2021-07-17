# Neural_Network_Charity_Analysis

# Overview of the analysis: 
## Explain the purpose of this analysis.
Alphabet Soup is a nonprofit organization which is helping the organization that protect the environment, improve people's well-being, and unify the world.
Soup has araised and donated over 10 billion dollars in the past 20 years. This money has been used to invest in lifesaving technogolies and organize reforestation groups around the world. In this study we are working on analysis the entire organization to analyze the impact of each donation so the Alphabet Soup group can ensure that the foundation's money is being used effectively. This can help the company's president to predict which organizations are worth dontating to and which are too high risk

## Modeling process description and Results: 

#### Data source that we used contains the following info:

- EIN and NAME—Identification columns
- APPLICATION_TYPE—Alphabet Soup application type
- AFFILIATION—Affiliated sector of industry
- CLASSIFICATION—Government organization classification
- USE_CASE—Use case for funding
- ORGANIZATION—Organization type
- STATUS—Active status
- INCOME_AMT—Income classification
- SPECIAL_CONSIDERATIONS—Special consideration for application
- ASK_AMT—Funding amount requested
- IS_SUCCESSFUL—Was the money used effectively
- Using bulleted lists and images to support your answers, address the following questions.
### Preproccessing the dataset
#### Target Variable:
- IS_SUCCESSFUL choosed for target variable

#### Features variables:

- APPLICATION_TYPE—Alphabet Soup application type
- AFFILIATION—Affiliated sector of industry
- CLASSIFICATION—Government organization classification
- USE_CASE—Use case for funding
- ORGANIZATION—Organization type
- STATUS—Active status
- INCOME_AMT—Income classification
- SPECIAL_CONSIDERATIONS—Special consideration for application
- ASK_AMT—Funding amount requested

#### NON useful variables:
- For this study EIN and NAME-Identification is not useful and we removed those from input data.
##### After removing non useful data, we used binning method to balance the data in better shape so our modeling have better output. 
#### By finding the total unique value in each columns we check the density of each category and based on the result recategorized the value in each column.

![Uniq_value](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/unique_values.png)

![APP_uniqe](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/App_value_count.png)

![APP_Dens](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/app_dens.png)

![Class_Dens](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/class_dense.png)


#### Next step is to find any categorical data in dataset and encode them to binary value.
#### We used OnHotEncoder for this purpose.

![Cat](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/category_list.png)

![encoded](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/encode.png)

## Compiling, Training, and Evaluating the Model
### We used TensorFlow libarary and Keras module to model our dataset. 
#### Hidden Layer
- We used Two hidden layer model for first attempt.
#### Activation 
- For hidden layer we used RELU activation to make all nonlinear values can fit properly in model
- For Target we used SIGMOID activation because the result should be binary.
Structure of our the model is as below:

![struct](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/complie.png)

### Model Evaluation 

![evaluate](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/evaluate.png)

### Optimize the model
#### To get the better performance from the model, we made some changes in our model
- In input data we reclassified the ASK_AMT column because of big difference amount of unique value compare to other columns. 
![ASK_AMT](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/unique_values.png)

- We add two more hidden layer to determine if the accuracy of the model increased or not

- We changed the activation also to determine the efficiency of the output

- We also increased the number of epoch from 50 to 100 to provide more data into the model and determin the result

![struct_opt](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/structure_opt.png)

![Accuracy_opt](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/accurancy_opt.png)

## Summary: 
In summary the best accuracy that we achieved in this model is 74% which is not really accepatable, even by optimizing the model we could not reach the better result at the end. 
Because our dataset structure is like a tabular data and also we dont have any images or natural language data I recomend using Random forest classifiers for this dataset to examine if that model can increase the accuracy of the output. 
Random forest models use a number of weak learner algorithms (decision trees) and combine their output to make a final classification (or regression) decision. Structurally speaking, random forest models are very similar to their neural network counterparts. Random forest models have been a staple in machine learning algorithms for many years due to their robustness and scalability. Both output and feature selection of random forest models are easy to interpret, and they can easily handle outliers and nonlinear data.
