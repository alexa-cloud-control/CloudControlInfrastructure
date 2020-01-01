## Create basic resources for CloudControl

Prepare AWS environment for CI/CD and Sandbox

### Components

This repo contains two cloudFormation templates

* template_cc_cloudformation.yml - base configuration for CI/CD, Lambdas and CloudControl
* sandbox-vpc.yml - Sandbox network configuration used in demo session

### Usage

This repository is ready to be run through TravisCI. 

First, lint tests are run against all templates, and CF stacks are deployed to AWS account

### Variables

You need to set variables as follows:

* account_number - YOUR AWS account ID
* AWS_ACCESS_KEY_ID - AWS user access key
* AWS_SECRET_ACCESS_KEY - secret for this user
* artifact_bucket - S3 bucket, where Lambda functions code will be stored
* deploy_table - DynamoDB table, where the hashes of Lambda functions will be stored (not used now)
* dynamodb_context - DynamoDB table for CloudControl context data
* terraform_region - region where CloudControl is deployed (it contains terraform in name, as legacy part of the project)

### Execution

Two CloudFormation stacks will be created:
* Alexa-CloudControl-Infrastructure
* Alexa-CloudControl-Sandbox

All important data is exported through Output section of CF stacks