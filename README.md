## Objective**: Implement an Artificial Neural Network (ANN) for cardiac signal
classification using either PyTorch or Keras. Follow the steps outlined below to complete
the assignment.
## Step 1: 
Dataset Loading: Load the provided cardiac signal dataset using ‘np.load’.
Dataset Link:
## Step 2:
Data Preparation: Combine the two files into a single dataset. Append file into
one.
## Step 3:
Signal Preprocessing: Apply the provided preprocessing function to the dataset:
## Step 4: 
Ground Truth Creation: Generate Y_data (ground truth) for classification:
Y_data=[0]*200+[1]*200
## Step 5: 
Data Splitting: Divide the dataset into training and testing sets.
## Step 6:
Model Construction:
• Design and implement an ANN model with a minimum of 5 layers.
• Ensure that you use the ReLU activation function.
##Step 7: 
Training and Testing: Evaluate the model by testing it for both 10 and 50 epochs.
## Step 8:
Model Saving: Save the trained model.
##Step 9: 
Evaluation Metrics: Generate a confusion matrix. Calculate precision, recall, and
accuracy.
Signal Preprocessing: use this.
def augtime(xdatat):
X_data=[]
for i in range(0,len(xdatat)):
if len(xdatat[i])<20000:
tem=np.append(xdatat[i],xdatat[i][0:(20000-len(xdatat[i]))])
while len(tem)<20000:
tem=np.append(tem,xdatat[i][0:(20000-len(tem))])
else:
tem=xdatat[i]
X_data=np.append(X_data,tem,axis=0)
X_test=np.reshape(X_data,(len(xdatat),20000,1))
return X_test
DataSet Details:
• The dataset consists of normal and abnormal cardiac sounds.
• Sample rate: 14,000 Hz.
• Butterworth filter settings: Low-cut: 200 Hz, High-cut: 20 Hz.
