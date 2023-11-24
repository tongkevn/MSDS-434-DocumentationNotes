# Module 3: Platform as a Service and Containerized Development  in Cloud Native

Purpose:

For your third demonstration assignment, complete both of the following tasks:

- construct applications on the GCP GAE (PAAS) and GCP Cloud instances.
- construct applications on AWS Elastic Beanstalk  and AWS EC2.

Include implementation of Containerized services using the Docker utility.


# Google Cloud Platform Notes
[Click Here to Access GCP Recording](https://northwestern.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=49788b87-e03e-4782-ae70-b09300052aeb)

Requirements:
- [Google Cloud Platform Repository Sample](https://github.com/GoogleCloudPlatform/python-docs-samples/tree/main/appengine/standard_python3/hello_world)
- New Google Cloud Project 

- Enable Cloud Build API
- Activate Cloud Shell
- Run the following commands in the shell

```
gclouds projects list
gcloud config set project <project ID>

```

- search API & Services in search bar
	- search and enable app engine admin API

```
sudo git clone git clone https://github.com/GoogleCloudPlatform/python-docs-samples.git

cd python-doc-samples/
ls
cd appengine/standard_python3/helloworld/

gcloud app deploy app.yaml
choose appropriate region

```

- Check deployed URL to see if the app was successfully deployed
- Search IAM and Admin
	- Search settings
	- Shut down project


# Amazon Web Services (AWS) Notes
[Click Here to Access AWS Recording](https://northwestern.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=09abc98d-5be1-4f87-af54-b093010b405c)

- Launch a t2.micro instance with an added key pair
- Access SSH from your putty client
- Run the following shell commands

```
mkdir test
cd test\

# install docker
sudo snap install docker


# create main.go
vi main.go

# create DockerFile
vi DockerFile

sudo docker build -t golangdockertest
sudo docker run
sudo docker run -p 8080:8080  -tid golangdockertest

```

- check in AWS if app was deployed (be sure that all traffic is allowed via security group)
- use public ipv4 DNS:<port_number>
- next run the following shell commands

```
sudo apt install git
zip files.zip *

```

- download the zip with an SFTP client (e.g. Termius)
- Setup IAM role to access required ElasticBeanstalk permission policies
- Search for Elastic BeanStalk
	- Create a new application
	- Set managed application platform as Docker
	- Upload zip file
	- Create a new service role
	- The rest of the settings can be the default...
- Click the domain URL to see if the app launched
- Shut down the necessary resources

