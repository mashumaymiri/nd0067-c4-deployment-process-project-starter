# Infrastructure description
This file explains the different infrastructures the application needs to run, such as RDS, S3 and Elastic Beanstalk.

## RDS
Realational Database Service provided by Amazon, allows the developer to create and manage databases in the cloud. 

The application runs its postgres database using RDS with the following properties:

* Database creation method:	Standard create.
* Engine option:	PostgreSQL 12 or 13
* Templates:	Free tier
* Database name:	postgres
* Public access: YES
* Database port: 5432
* Initial database name: postgres

## S3
The Amazon S3 (Simple Storage Service), allows the developer to create a bucket and store files in it.

On each deployment the application uploads the frontend Angluar files to the bucket, then the user can access those files to see the web page. The S3 bucket is created with the following properties:

* Bucket name: mashumaymiribucket
* AWS Region: us-east-1
* Object Ownership: ACLs enabled
* Block all public access: No

## Elastic Beanstalk

The AWS Elastic Beanstalk allows developers to create, run and configure thourgh CLI commands.

This allows the application to run a pipeline on each change that happens on the github repository. 

The backend application runs on the Elastic Beanstalk environment (Udagramapi-env).

# 

![Alt text](An%20architecture%20diagram%20showing%20a%20high-level%20overview%20of%20the%20infrastructure.png)