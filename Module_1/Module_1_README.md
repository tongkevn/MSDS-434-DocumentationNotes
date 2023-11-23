# Module 1: Introduction to Cloud Native Platforms
Purpose: For your first demonstration video assignment, create and share a demo video in which you show:

- the creation of an instance on the Google Cloud Platform.
- the creation of an instance on Amazon AWS.


# Google Cloud Platform Notes
[Click here for Module 1 GCP Video](https://northwestern.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=42157156-b5df-48bb-86ac-b08401812692)

- Create a project in Google Cloud
- Search for and enable Compute Engine API
- Once Compute Engine API finishes loading, click “Create Instance”
- Create an Instance Name
- Choose Region and Zone that is closest to where you live
- For lowest cost configuration, use E2 and E2 micro type
- The rest of the Instance settings can remain as default
- Create the instance and wait until the instance is finished generating
- Once generated, the instance can be deleted with the “More Actions” settings in the list of all the VM Instances

# Amazon Web Services (AWS) Notes
[Click here for Module 1 AWS Video](https://northwestern.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=50cb1e6f-d55a-4ef2-b912-b0850002c73a)

- Search and launch EC2 tool
- Choose launch instance
- Create a name for the instance
- Select Ubuntu for the machine and t2.micro for instance type
- Select and create a key pair (in Putty format) for additional security
- Launch instance

## Access AWS Shell
- In Putty client, copy / paste instances’ Public IPv4 address
- Import key pair file
- Login into instance (default username is ubuntu)
- Once login is verified, terminate instance in AWS 
