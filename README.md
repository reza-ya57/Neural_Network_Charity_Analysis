# Neural_Network_Charity_Analysis

# Overview of the analysis: 
## Explain the purpose of this analysis.
Alphabet Soup is a nonprofit organization which is helping the organization that protect the environment, improve people's well-being, and unify the world.
Soup has araised and donated over 10 billion dollars in the past 20 years. This money has been used to invest in lifesaving technogolies and organize reforestation groups around the world. In this study we are working on analysis the entire organization to analyze the impact of each donation so the Alphabet Soup group can ensure that the foundation's money is being used effectively. This can help the company's president to predict which organizations are worth dontating to and which are too high risk

## Results: 

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
#### Target Variable
- IS_SUCCESSFUL choosed for target variable

#### Features variables
##### Below variables choosed for features to run the model:
- APPLICATION_TYPE—Alphabet Soup application type
- AFFILIATION—Affiliated sector of industry
- CLASSIFICATION—Government organization classification
- USE_CASE—Use case for funding
- ORGANIZATION—Organization type
- STATUS—Active status
- INCOME_AMT—Income classification
- SPECIAL_CONSIDERATIONS—Special consideration for application
- ASK_AMT—Funding amount requested

#### NON useful variables
##### For this study EIN and NAME-Identification is not useful and we removed those from input data.
##### After removing non useful data, we used binning method to balance the data in better shape so our modeling have better output. 
#### By finding the total unique value in each columns we check the density of each category and based on the result recategorized the value in each column.

![Uniq_value](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/unique_values.png)

[APP_uniqe](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/App_value_count.png)

[APP_Dens](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/app_dens.png)

[Class_Dens](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/class_dense.png)


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
![ASK_AMT]()

- We add two more hidden layer to determine if the accuracy of the model increased or not

- We changed the activation also to determine the efficiency of the output

- We also increased the number of epoch from 50 to 100 to provide more data into the model and determin the result

![struct_opt](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/structure_opt.png)

[Accuracy_opt](https://github.com/reza-ya57/Neural_Network_Charity_Analysis/blob/main/images/accurancy_opt.png)



Compiling, Training, and Evaluating the Model
How many neurons, layers, and activation functions did you select for your neural network model, and why?
Were you able to achieve the target model performance?
What steps did you take to try and increase model performance?
Summary: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.


With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to help Beks create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, Beks received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as the following:

EIN and NAME—Identification columns
APPLICATION_TYPE—Alphabet Soup application type
AFFILIATION—Affiliated sector of industry
CLASSIFICATION—Government organization classification
USE_CASE—Use case for funding
ORGANIZATION—Organization type
STATUS—Active status
INCOME_AMT—Income classification
SPECIAL_CONSIDERATIONS—Special consideration for application
ASK_AMT—Funding amount requested
IS_SUCCESSFUL—Was the money used effectively
Results: Using bulleted lists and images to support your answers, address the following questions.

Data Preprocessing
What variable(s) are considered the target(s) for your model?
What variable(s) are considered to be the features for your model?
What variable(s) are neither targets nor features, and should be removed from the input data?
Compiling, Training, and Evaluating the Model
How many neurons, layers, and activation functions did you select for your neural network model, and why?
Were you able to achieve the target model performance?
What steps did you take to try and increase model performance?
Summary: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.
