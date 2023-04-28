# Prediction-numbers-children-in-household
<p>Given a dataset of different households, we will try to predict how many children live in a household.<br>
For that, we create a Neural Net <ins>from scratch</ins> in Python 3, train it, test its performance.<br>
The method we use is regression.<br>
We use the obtained weights to create a function to give predictions on households of new data.</p><br>


<p>We extract the following features as columns from the dataset:

1. ID of Instance
2. Sex of the chef of the house
3. Age of this chef
4. Marital status of this chef
5. Stands for weather the spouse lives in the same household or not
6. Belonging to a special ethnicity
7. Number of children
8. Number of persons living in the household
9. Income of the household
10. Number of rooms in which the persons of the household sleep</p><br>


Columns chosen as Input for our Neural Network:<br>
* 2 | 3 | 4 | 5 | 6 | 9 | 10<br><br>


Architecture of Neural Net:<br>
* Input: Matrix consisting of columns, each standing for the data of one household.<br>
* Hidden-Layer: 1 Hidden-Layer with the Leaky ReLU as Activation Function.<br>
* Output: Output-Layer has Dimension 1 and contains no Activation Function.<br><br>


Validation:<br>
* Label: We use column number 7 as label of our data.<br>
* Error-Function: We use the Mean-Squarred-Error.<br><br>


Update Parameters:<br>
* Gradient Descent<br><br>


Dataset-Split:<br>
* Trainingset: 60.000 training samples<br>
* Testset: 28.713 test samples<br><br>


Results:<br>
* Training Error: 0.56<br>
* Test Error: 0.56<br><br>


Comment:<br>
* When Column 8 (Number of persons living in the household) is chosen, too, Errors can easily be reduced to 0.20 or even less.<br>
* Nevertheless, one could argue that this column contains to much information about what we want to predict already, which is why we decided to leave it out.<br><br>


Label New Data:<br>
* The function label_new_data gives an estimation about how many children live in a new household given its data.<br>
* For this it uses the learned weights, going forward through the Neural Net one time and rounding the result to an integer.
