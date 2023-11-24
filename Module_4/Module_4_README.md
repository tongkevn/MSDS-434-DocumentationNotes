# Module 4: Cloud-Native Database Choice and Design
Purpose:

- Construct a demonstration of a data ingest into Google Big Query data warehouse and demonstrate active queries against the data warehouse.
- Construct a demonstration of a data ingest into Amazon Redshift and generate an application.


# Google Cloud Platform Notes
[Click here to access the GCP recording](https://northwestern.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=c19827da-196e-4621-b67c-b099006d968c)

- search for buckets in GCP search bar
- create bucket
	- give the bucket a name
	- select an appropriate region
- create the necessary folders in the bucket
- use the upload files button to upload the necessary files
- access Permissions tab and grant access to allUsers
- search Big Query
	- Add data source
	- Search in Google Cloud Storage for the bucket & file
	- Create a new dataset
		- give it a name, region etc.
- run some SQL test queries


# Amazon Web Services Notes
[Click here to access the AWS recording](https://northwestern.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=2241a91f-44be-4b88-925c-b09800682868)

- search for Redshift
- Open query editor
- In the Serverless dropdown, search for sample_dev_data and pick a dataset sample
- Once the dataset is loaded, ensure that you are running the query on the correct dataset, and then you will be able to run SQL queries as needed
