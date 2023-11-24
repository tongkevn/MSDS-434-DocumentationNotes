# Module 5: Applied Data Engineering

Purpose:
- construct a demonstration of a data ingest and execution of Google Big Query ML or Amazon Sagemaker ML.


# Amazon Web Services Sagemaker Notes
[Click Here to Watch the AWS Sagemaker Recording](https://northwestern.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=883cb64c-acb6-49dc-b522-b0a000050056)

[Click Here to Access the XG Boost code provided by AWS](https://docs.aws.amazon.com/sagemaker/latest/dg/xgboost.html)

- A Jupyter notebook is also available in this repository for reference.

## Data Preparation
For AWS the following steps need to be taken before ingestion
- one hot encoding
- move prediction variable to the first row in the dataframe
- delimiter is a comma (",")

## AWS Storage
- upload the CSV to an S3 bucket

## Sagemaker
- Search for Sagemaker, and setup appropriate region and IAM roles
- Once setup, open Jupyterlabs in Sagemaker
- Run the following Python code to:
	- Read the CSV
	- Create the training, validation, and test dataset
	- Generate the predictive (XGBoost) model
	- Delete the endpoint


```
bucket = 'bankmarketingfull'
prefix = 'bankmarketingfull/xgboost'
# Define IAM role
import boto3
import re
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import os
import sagemaker
from sagemaker import get_execution_role
from sagemaker.inputs import TrainingInput
from sagemaker.serializers import CSVSerializer

role = get_execution_role()


dataset = pd.read_csv('s3://bankmarketingfull/bank_full_enc.csv')


train_data, validation_data, test_data = np.split(dataset.sample(frac=1, random_state=1729), [int(0.7 * len(dataset)), int(0.9 * len(dataset))])
train_data.to_csv('train.csv', header=False, index=False)
validation_data.to_csv('validation.csv', header=False, index=False)


boto3.Session().resource('s3').Bucket(bucket).Object(os.path.join(prefix, 'train/train.csv')).upload_file('train.csv')
boto3.Session().resource('s3').Bucket(bucket).Object(os.path.join(prefix, 'validation/validation.csv')).upload_file('validation.csv')
s3_input_train = TrainingInput(s3_data='s3://{}/{}/train'.format(bucket, prefix), content_type='csv')
s3_input_validation = TrainingInput(s3_data='s3://{}/{}/validation/'.format(bucket, prefix), content_type='csv')


containers = {'us-west-2': '433757028032.dkr.ecr.us-west-2.amazonaws.com/xgboost:latest',
              'us-east-1': '811284229777.dkr.ecr.us-east-1.amazonaws.com/xgboost:latest',
              'us-east-2': '825641698319.dkr.ecr.us-east-2.amazonaws.com/xgboost:latest',
              'eu-west-1': '685385470294.dkr.ecr.eu-west-1.amazonaws.com/xgboost:latest'}

sess = sagemaker.Session()
xgb = sagemaker.estimator.Estimator(containers[boto3.Session().region_name],
                                    role, 
                                    instance_count=1, 
                                    instance_type='ml.m4.xlarge',
                                    output_path='s3://{}/{}/output'.format(bucket, prefix),
                                    sagemaker_session=sess)


xgb.set_hyperparameters(eta=0.1, objective='binary:logistic', num_round=25) 
xgb.fit({'train': s3_input_train, 'validation': s3_input_validation})


xgb_predictor = xgb.deploy(
	initial_instance_count = 1,
	instance_type = 'ml.m4.xlarge',
	serializer = CSVSerializer())


def predict(data, rows=500):
    split_array = np.array_split(data, int(data.shape[0] / float(rows) + 1))
    predictions = ''
    for array in split_array:
        predictions = ','.join([predictions, xgb_predictor.predict(array).decode('utf-8')])

    return np.fromstring(predictions[1:], sep=',')

predictions = predict(test_data.to_numpy()[:,1:])
predictions


xgb_predictor.delete_model()
```
