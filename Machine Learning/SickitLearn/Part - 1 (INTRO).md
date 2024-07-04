- - -
### Installing Sickit-learn
![[Pasted image 20240302091504.png|800]]

![[Pasted image 20240302091812.png|800]]
X -> are our features of the house
Y -> Predictions or Output
We pass the data X into the model , learn the pattern and predict Y using X.

### The Model has to learn from the data. So, there are primarily two phases ->
1. We CREATE the Model. 
 - In sickit - learn , all Models are Python Objects.

2. The Model has to learn from the data.
 - Often called the .fit(X,Y) step.  

### The Prediction
![[Pasted image 20240308200723.png|500]]
We can see that the model is somewhat noisy , this is because the one of the features can be in thousands(like price) while another feature can be in single or double digits. So, the feature with the larger value will have greater effects.
SO, we have to apply 'SCALING'.(Pre-processing)
![[Pasted image 20240308201138.png|700]]

### After Scaling (Looks a lot better)->
![[Pasted image 20240308201953.png|600]]
This Standard Scaling does not make the scales of X and Y axis exactly the same.
## But we have a major problem
We are predicting and judging the model based on the same values that IT HAS TRAINED ON.

## Solution
![[Pasted image 20240308220049.png]]
We will divide the dataset into 3 instances. Each instance will have three parts 
- Two parts will contain the values which will be used for "Training".
- One part will be used to predict and judge the model.

![[Pasted image 20240308220704.png|800]]
The GridSearch CV OBJECT will take care of it.
- We will give it a 'pipeline' and we can give it a 'grid' like number of neighbours.
- And it will perform Cross-validation.

![[Pasted image 20240309063537.png|800]]


