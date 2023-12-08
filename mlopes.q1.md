## Scenario 
The Data Science team built a model for classifying customer to two buckets churn and loyal.
The model is based on xgboost, and the business unit approved the model.
The Data Scientist handed it over as a Sckit-learn Pipeline and model as a Pickle file.

The training data is available in a database (MySQL).
The Business Unit is looking for support in:

- Create a data pipeline for Inference
- Create an inference API service (Scalable) 

Model Details:
- Libraries: Python 3.10, sckit-learn, xgboost, pandas
- Inference memory consumption per record 50 MB
- Model Load memory: 1.2 GB


Non Functional Requirments
- Every five minutes, the API will be hit between 100 to 500 requests from a UI
- The overall compute cost should maintain minimum and elastic with scalability to accommodate peak request 
- Every 90 days, a new model will be deployed with zero downtime
- Availability of the API should be 99.9999%
