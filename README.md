## Implementation-of-Logistic-Regression-Using-Gradient-Descent
## AIM:
To write a program to implement the the Logistic Regression Using Gradient Descent.

## Equipments Required:
Hardware – PCs
Anaconda – Python 3.7 Installation / Jupyter notebook
## Algorithm
STEP 1.Prepare your data - Clean and format your data - Split your data into training and testing sets

STEP 2.Define your model - Use a sigmoid function to map inputs to outputs - Initialize weights and bias terms

STEP 3.Define your cost function - Use binary cross-entropy loss function - Penalize the model for incorrect predictions

STEP 4.Define your learning rate - Determines how quickly weights are updated during gradient descent

STEP 5.Train your model - Adjust weights and bias terms using gradient descent - Iterate until convergence or for a fixed number of iterations

STEP 6.Evaluate your model - Test performance on testing data - Use metrics such as accuracy, precision, recall, and F1 score

STEP 7.Tune hyperparameters - Experiment with different learning rates and regularization techniques

STEP 8.Deploy your model - Use trained model to make predictions on new data in a real-world application.

## Program:
/*
```
Program to implement the the Logistic Regression Using Gradient Descent.
Developed by: bala murugan s
RegisterNumber: 212223230027
*/
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

dataset=pd.read_csv("/content/Placement_Data.csv")
dataset

dataset=dataset.drop('sl_no',axis=1)
dataset=dataset.drop('salary',axis=1)

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder ()
dataset ["gender"]=dataset ["gender"]. astype ('category' )
dataset["ssc_b"]=dataset ["ssc_b"].astype ('category')
dataset["hsc_b"]=dataset ["hsc_b"].astype( 'category')
dataset ["hsc_s"]=dataset["hsc_s"].astype( 'category')
dataset["degree_t"]=dataset ["degree_t"]. astype( 'category' )
dataset ["workex"]=dataset ["workex"].astype ('category')
dataset["specialisation"]=dataset ["specialisation"]. astype( 'category')
dataset["status"]=dataset ["status"].astype ('category')
dataset.dtypes

dataset["gender"]=dataset ["gender"]. cat. codes
dataset["ssc_b"]=dataset["ssc_b"]. cat .codes
dataset["hsc_b"]=dataset ["hsc_b"]. cat. codes
dataset["hsc_s"]=dataset ["hsc_s"] . cat. codes
dataset["degree_t"]=dataset ["degree_t"]. cat. codes
dataset ["workex"]=dataset ["workex"]. cat. codes
dataset["specialisation"]=dataset["specialisation"].cat. codes
dataset ["status"]=dataset ["status"]. cat. codes
dataset

X=dataset.iloc[:,:-1].values
Y=dataset.iloc[:,-1].values
Y

theta=np.random.randn(X.shape[1])
y=Y
def sigmoid(z):
  return 1/(1+np.exp(-z))
def loss(theta,X,y):
  h=sigmoid(X.dot(theta))
  return -np.sum(y*np.log(h)+(1-y)*log(1-h))

def gradient_descent(theta, X,y, alpha, num_iterations):
    m=len(y)
    for i in range(num_iterations):
        h=sigmoid(X.dot(theta))
        gradient=X.T.dot(h-y)/m
        theta-alpha*gradient  
    return theta
theta=gradient_descent(theta, X, y, alpha=0.01, num_iterations=1000)
def predict(theta,X):
    h=sigmoid(X.dot(theta))
    y_pred=np.where(h>=0.5,1,0)
    return y_pred
y_pred=predict(theta,X)

accuracy=np.mean(y_pred.flatten()==y)
print('Accuracy:',accuracy)

print(y_pred)

print(Y)

xnew=np.array([[0,87,0,95,0,2,78,2,0,0,1,0]]) 
y_prednew=predict(theta, xnew) 
print(y_prednew)

xnew=np.array([[0,0,0,0,0,2,8,2,0,0,1,0]])
y_prednew=predict(theta, xnew) 
print(y_prednew)
```
## Output:
![Screenshot 2024-09-06 113618](https://github.com/user-attachments/assets/ea8cc588-25f8-4c8c-a774-cbe3de1e0f32)

![Screenshot 2024-09-06 113625](https://github.com/user-attachments/assets/5ec31111-8f0d-47a8-9c0d-da32c83986c2)

![Screenshot 2024-09-06 113628](https://github.com/user-attachments/assets/7f9346f1-61ca-4fe8-bffd-46f7977984a7)


## Result:
Thus the program to implement the the Logistic Regression Using Gradient Descent is written and verified using python programming.

