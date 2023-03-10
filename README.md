<h2 align="center">Auto tag AWS solution deployed with Terraform</h2>

<h4 align="center"></h4>

<h2 align="center">Technical overview</h2>

This solution uses an automated workflow to tag newly created resources. When an AWS resource is created a corresponding event is logged by AWS Cloudtrail. This event will be captured by Eventbridge and trigger a rule set to monitor selected events. The triggered rule sends the event to a Lambda function to be processed. The Lambda function identifies the name of the IAM user or role that created the resource and tags the resource with the same name and any associated tags applied to the user or role.

## Pre-requisites

- Terraform CLI (1.0+) installed
- An AWS account and user account with admin permissions
- AWS CLI (2.0+) installed

## Deployment Steps

```bash
git clone && cd aws-autotag
terraform init
terraform plan
terraform apply --auto-approve
```
