# insurance_claims_fraud_Detection

Design plans for hosting and deployment of ML models on Azure Analytics Platform:

Approach 1:

Azure has a provision for platforms such as Azure Machine Learning Studio that can be used to train and deploy models. The best part of this solution is that GPU resources will be provided as well for training.

However, this might be an overkill for our purpose of insurance claims fraud detection as the models are simple don’t require high computational power. And also as the data is not large.


Approach 2:

The models can be deployed as Docker containers, however this approach also may be an overkill in our case, this requires high maintenance and is preferred in cases where models are complex

Approach 3 (Best):

In this approach, instead of training models, we are going to deploy models pre-trained on our local machine by saving the pre-trained model in a pkl file. We will just need to upload: 
1. The pkl file with pre-trained model weights, 
2. a YAML file that includes the dependencies, and 
3. a py file to load the model and make predictions.

They can be packaged and a single end-point is created. Clients can then make a call to receive the output predictions from the model. "Key & token" based-authentication is provided.
