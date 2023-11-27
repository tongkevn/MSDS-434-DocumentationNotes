# Module 10: Final Deployment and Maintenance

Purpose: construct a demonstration of GitHub actions in support of continuous development.

# Amazon Web Services Notes
[Click Here to Access AWS Recording](https://northwestern.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=7bc9ef2d-7f8a-48cd-882d-b0c2014ecda8)


Note: I opted to use [AWS Serverless Application Model (SAM)](https://aws.amazon.com/serverless/sam/) instead of GitHub Actions

Requirements needed:
- Visual Studio Code
- AWS Command Line Interface
- SAM Command Line Interface
- Docker
- AWS Toolkit for VS Code

## SAM
- Open VS Code command palette and select "Create Lambda SAM Application"
	- For my project I used Python 3.7 as my language
- Opt for the AWS SAM Hello World option for a great starter to build a lambda function
- The necessary .yaml and .py files are created. All you have to do is update the app.py file with the necessary code for your lambda function
- Open the app.py file update the function as needed (my version is available in this repository)
- Run the following command in the terminal

```
sam deploy --guided
```
- choose a stack name and region, and deploy
- Open the AWS Lambda console online to see if the Lambda Function deployed
