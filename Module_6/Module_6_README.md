# Module 6: Managed Machine Learning Platforms

Purpose:
- construct a demonstration of the construction of an autoML application using either GCP BigQuery or AWS Sagemaker Autopilot.

# Amazon Web Services (AWS) Notes
[Click Here to Access AWS Recording](https://northwestern.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=fbe8b3f0-5818-45bd-9fae-b0a8001a2466)

Note: This service is extremely expensive and is therefore not recommended for modeling. If you do run the models, be sure to delete the AWS domains and endpoints as necessary.

- https://docs.aws.amazon.com/sagemaker/latest/dg/gs-studio-delete-domain.html
- https://docs.aws.amazon.com/sagemaker/latest/dg/domain-user-profile-add-remove.html
- https://docs.aws.amazon.com/sagemaker/latest/dg/canvas-manage-apps.html


## AWS Sagemaker Autopilot
- Ensure CSV delimiter is a comma (",")
- Upload CSV to bucket
- In Sagemaker, create an autopilot experiment
	- Create a name
	- Choose the created CSV in the appropriate bucket
	- Autosplit the data
	- Choose the target column
	- Select "Auto" for training method and algorithms
	- Do not auto deploy
