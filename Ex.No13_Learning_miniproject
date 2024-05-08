# Ex.No: 13 Learning – Use Supervised Learning  
### DATE: 22/04/24                                                                           
### REGISTER NUMBER : 212221040109
### AIM: 
To write a program to train the classifier for diabeties.
###  Algorithm:
Step 1: Load the diabetes dataset.<br>
Step 2: Split the dataset into features (input) and target variable (output).<br>
Step 3: Split the data into training and testing sets.<br>
Step 4: Scale the features using StandardScaler.<br>
Step 5: Train a neural network classifier on the training data.<br>
Step 6: Evaluate the classifier's accuracy on both training and testing data.<br>
Step 7: Create a function to predict diabetes based on user input.<br>
Step 8: Launch a Gradio interface for users to input their data and get a prediction.<br>
Step 9: Stop the program.<br>
### Program:
```py
#import packages
import numpy as np
import pandas as pd
import gradio as gr
import pandas as pd
data = pd.read_csv('diabetes.csv')
data.head()
x = data.drop(['Outcome'], axis=1)
y = data['Outcome']
print(x[:5])

from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test= train_test_split(x,y)

#scale data
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
x_train_scaled = scaler.fit_transform(x_train)
x_test_scaled = scaler.fit_transform(x_test)

#instatiate model
from sklearn.neural_network import MLPClassifier
model = MLPClassifier(max_iter=1000, alpha=1)
model.fit(x_train, y_train)
print("Model Accuracy on training set:", model.score(x_train, y_train))
print("Model Accuracy on Test Set:", model.score(x_test, y_test))

#create a function for gradio
def diabetes(Pregnancies, Glucose, Blood_Pressure, SkinThickness, Insulin, BMI,Diabetes_Pedigree, Age):
    x = np.array([Pregnancies,Glucose,Blood_Pressure,SkinThickness,Insulin,BMI,Diabetes_Pedigree,Age])
    prediction = model.predict(x.reshape(1, -1))
    if(prediction==0):
      return "NO"
    else:
      return "YES"

outputs = gr.Textbox()
app = gr.Interface(fn=diabetes, inputs=['number','number','number','number','number','number','number','number'], outputs=outputs,description="Detection of Diabeties")
app.launch(share=True)

```


### Output:
![image](https://github.com/nagaraj6618/AI_Lab_2023-24/assets/127173574/bb5b23d7-7192-474e-b0cc-06018e21da30)


### Result:
Thus the system was trained successfully and the prediction was carried out.
