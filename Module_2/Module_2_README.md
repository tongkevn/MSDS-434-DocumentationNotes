# Module 2: Workflow Development
Purpose:

For your second demonstration assignment, create and share a brief demo video in which you complete the following tasks using both Google Cloud Platform and Amazon Web Service EC2. Use the demonstration videos in this week’s lecture page for reference.

- demonstrate a project creation (either following the provided demo or a project of your own choosing)
- push the project to a GitHub repository
- edit your project
- push updates back to GitHub

# Google Cloud Platform Notes
[Click Here to access GCP Video](https://northwestern.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=1d30c314-51e3-4686-b8de-b08b000b39e9)

- Requirements:
	- Enable Compute Engine API
	- A Github repository that you would like to clone / update
	- An empty Github repository to push code to
	- An access token from GitHub
- Create virtual machine instance with Compute Engine
- Open up a SSH shell by clicking “SSH” in VM Instances window
- Run the following commands to clone, push, and make changes to repository:

```
# install git
sudo apt update
sudo apt install git

# clone repository that you want to copy
git clone <insert GitHub url>

# push repository to new empty repository
git init
git branch -M main
git remote remove origin
git remote add origin http://<username>:<access token><empty repository url>
git push -u origin main

# make changes to repository
vi <filename>

# push repository
git add <filename>
git commit -m “add comments here”
git push -u origin main

```

# AWS Notes
[Click Here to Access AWS Video](https://northwestern.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=2d655b04-6496-4bf9-9516-b08b00772f2e)

- Launch an t2.micro instance within EC2, and add a key pair for login security
- Access the newly created instance with a putty client (e.g. Putty or Termius)
- Run the following commands to clone, push, and make changes to repository:

```
# check git is installed
git -- version

# clone repository that you want to copy
git clone <insert GitHub url>

# push repository to new empty repository
git init
git branch -M main
git remote remove origin
git remote add origin http://<username>:<access token><empty repository url>
git push -u origin main

# make changes to repository
vi <filename>

# push repository
git add <filename>
git commit -m “add comments here”
git push -u origin main

```
