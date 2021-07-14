# Prediction-numbers-children-in-household
Given a dataset of different households, we will try to predict how many children live in a household.
For that we create a Neural Net in python, train it, test its performance.
The method we use is regression.
We use the obtained weights to create a function to give predictions on households of new data. 


We extract the following features as columns from the dataset:
1 ID of Instance
2 Sex of the chef of the house
3 Age of this chef
4 Marital status of this chef
5 Stands for weather the spouse lives in the same household or not
6 Belonging to a special ethnicity
7 Number of children
8 Number of persons living in the household
9 Income of the household
10 Number of rooms in which the persons of the household sleep

Columns chosen as Input for our Neural Network:
    2 | 3 | 4 | 5 | 6 | 9 | 10

Architecture of Neural Net:
    Input: Matrix consisting of columns, each standing for the data of one household.
    Hidden-Layer: 1 Hidden-Layer with the Leaky ReLU as Activation Function.
    Output: Output-Layer has Dimension 1 and contains no Activation Function

Validation:
    Label: We use column number 7 as label of our data.
    Error-Function: We use the Mean-Squarred-Error
    
Update Parameters: Gradient Descent

Dataset-Split:
    Trainingset: 60.000 training samples
    Testset: 28713 test samples
    
Results:
    Training Error: 0.56
    Test Error: 0.56
    
Comment: 
    When Column 8 (Number of persons living in the household) is chosen, too, Errors can easily be reduced to 0.20 or even less.
    Nevertheless, one could argue that this column contains to much information about what we want to predict already, which is why we decided to leave it out.
    
Label New Data:
    The function label_new_data gives an estimation about how many children live in a new household given its data.
    For this it uses the learned weights, going forward through the Neural Net one time and rounding the result to an integer.
