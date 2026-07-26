# CloudDocs API

CloudDocs is a cloud-native document management platform that provides secure user authentication, document management, and cloud storage integration.

This repository contains the backend API service built with Python Flask.

## Features

- User registration and authentication
- Email verification workflow
- Document upload and management
- Secure file storage with Amazon S3
- Metadata persistence with database services

## Architecture

The backend integrates with AWS managed services:

- Amazon S3 - document storage
- Amazon DynamoDB - verification token storage
- Amazon SNS - email notification service

## Tech Stack

- Python
- Flask
- SQL Database
- AWS SDK (boto3)
- AWS Services


## Webapp
Project introduction

## Requirements
python 3.6.x 

## Setup
1. Prerequisites for building and deploying your application locally.
   1. Config environment
      1. This project is based Python 3.6.x. 
      2. Both the virtualenv or the system env would be fine. 
   2. IDE
      1. Any IDE would be fine. 
      2. Pycharm is recommended.

2. Build and Deploy instructions for the web application.
   1. git pull {repo}
   2. Build and deploy
      1. Enter the {repo} directory.
      2. Checkout the branch.
      3. (After activate your virtualenv, ) pip install -r requirements.txt
      4. Run "python manage.py runserver -p 22928"

## Command
Connect RDB from EC2 instance
```
mysql -h csye6225.cpy2lc6qfkor.us-east-1.rds.amazonaws.com -u csye6225 -p

use csye6225;
show tables;
describe {tablename}
DROP TABLE IF EXISTS `accounts`;DROP TABLE IF EXISTS `alembic_version`;DROP TABLE IF EXISTS `documents`;
```

read python service log
```
sudo journalctl -u python.service -f
```

ec2 userdata script path
```
sudo cat /var/lib/cloud/instance/scripts/part-001
sudo /var/lib/cloud/instance/scripts/part-001
```

ec2 userdata re-run before cloud formation update stack
```
sudo rm -rf /var/lib/cloud/*
```

import ssl cert
```
aws acm import-certificate --certificate fileb://demo_xihou_me.crt --certificate-chain fileb://demo_xihou_me.ca-bundle --private-key fileb://private.key
```
