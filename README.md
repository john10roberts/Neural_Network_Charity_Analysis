# Neural_Network_Charity_Analysis
 Neural_Network_Charity_Analysis

## Overview of Project
Using the CSV file of more than 34,000 organizations that have received funding from Alphabet Soup over the years.  We will use machine learning and neural networks to predict the whether applicants will be successful or not. 

## Results
We began with a data set consisting of the following variables

* EIN - Dropped ID Column
* NAME - Dropped ID Column
* APPLICATION_TYPE
* AFFILIATION
* CLASSIFICATION
* USE_CASE
* ORGANIZATION
* STATUS
* INCOME_AMT
* SPECIAL_CONSIDERATIONS - Dropped Run #2
* ASK_AMT
* IS_SUCCESSFUL - Target Variable

### Data Preprocessing
For the initial run we dropped the EIN and NAME fields. For Run #2 we dropped the Special_Considerations field.  All of the remaning fields were used as features in the analysis.  Numeric fields were scaled using the standard scalar.  Character fields were converted to numeric values using the one hot encoder method.  Additionally we also binned some of the categorical variables (Application_Type, Classification) to make for a cleaner dataset. 

### Compiling, Training and Evaluating the Model

#### Attempt 1
* Two hidden layers
    * Layer 1 - 80 Neurons, relu activation
    * Layer 2 - 30 Neurons, relu activation
* Output Layer
    * Sigmoid Activation
I began by using 80 neurons in layer 1 which is around 2 times the number of fields in the input layer.  Then I used 30 neurons in layer two.  

![Accuracy](https://github.com/john10roberts/Neural_Network_Charity_Analysis/blob/main/Resources/Model1Acc.png)

The model had an accuracy of 72.8% which was short of the desired accuracy of 75%

#### Attempt 2
* Two hidden layers
    * Layer 1 - 80 Neurons, relu activation
    * Layer 2 - 30 Neurons, relu activation
* Output Layer
    * Sigmoid Activation
I began by using 80 neurons in layer 1 which is around 2 times the number of fields in the input layer.  Then I used 30 neurons in layer two.  This second attempt I dropped the SPECIAL_CONSIDERATION feature but kept the rest of the model the same. 

![Accuracy](https://github.com/john10roberts/Neural_Network_Charity_Analysis/blob/main/Resources/Model2Acc.png)

The model had an accuracy of 72.92% which was short of the desired accuracy of 75%

#### Attempt 3
* Two hidden layers
    * Layer 1 - 160 Neurons, relu activation
    * Layer 2 - 60 Neurons, relu activation
* Output Layer
    * Sigmoid Activation
I doubled the number of neurons in both layers in an attempt to improve accuracy. I also used the features from attempt #2 

![Accuracy](https://github.com/john10roberts/Neural_Network_Charity_Analysis/blob/main/Resources/Model2Acc.png)

The model had an accuracy of 72.99% which was short of the desired accuracy of 75%


#### Attempt 4
* Three hidden layers
    * Layer 1 - 160 Neurons, relu activation
    * Layer 2 - 60 Neurons, relu activation
    * Layer 3 - 30 Neurons, relu activation
* Output Layer
    * Sigmoid Activation
I added an additional layer and kept the same number of neurons from attempt 3. 

![Accuracy](https://github.com/john10roberts/Neural_Network_Charity_Analysis/blob/main/Resources/Model2Acc.png)

The model had an accuracy of 73.04% which was short of the desired accuracy of 75%

## Summary
While I was able to slightly improve accuracy in each subsequent attempt it never reached the 75% target accuracy.  To truly get a more accurate model more data would be needed to have the model be able to better interpret the results.  Because the target variable is binary we could have used a random forest model to see if the accuracy of that model was similar to the neural network.
