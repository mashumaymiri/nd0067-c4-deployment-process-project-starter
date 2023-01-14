# Pipeline description
The application runs the pipeline through CircleCi. The pipeline has three phases:
* build 
* hold
* deploy

## build
In this phase, the pipeline install dependencies, lints and builds the application: 

* Spin up enviroment: Starts the CircleCi enviroment
* Preparing enviroment variables: Gets the environment variables from project settings
* Install Node.js 14.15: Node.js is needed for installing dependencies and running the application
* Checkout code: Checks the code in the github repository
* Install Front-End Dependencies: Installs all the Front-End Dependencies
* Install API Dependencies: Installs all the API Dependencies
* Front-End Lint: Lints the Front-End application using ESlint
* Front-End Build: Builds the Front-End application
* API Build: Builds the API

![ALT Text](CircleCi%20build.png)

## hold
In this phase, the pipeline waits for the developers approval to continue the deployment of the application

![ALT Text](A%20diagram%20showing%20the%20overview%20of%20the%20pipeline.png)
## deploy
In this phase, the pipeline starts deploying the application to the AWS cloud using Elastic Beanstalk CLI:

* Spin up enviroment: Starts the CircleCi enviroment
* Preparing enviroment variables: Gets the environment variables from project settings
* Install Node.js 14.15: Node.js is needed for installing dependencies and running the application
* Setting Up Elastic Beanstalk CLI: The EB CLI is used to deploy the app to AWS.
* Install AWS CLI - latest: The AWS CLI is used to connect and upload the Front-End application to the S3 bucket
* Configure AWS Access Key ID: Access to the IAM user in the AWS cloud
* Checkout code: Checks the code in the github repository
* Deploy App: Deploys both the API and the Front-End application to the AWS cloud

![ALT Text](CircleCi%20deploy.png)
