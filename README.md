# Iac
Deploy single instance via CloudFormation
## Getting Started
### Validate
```
aws cloudformation validate-template --template-body file://root.yaml
aws cloudformation validate-template --template-body file://instance.yaml
aws cloudformation validate-template --template-body file://vpc.yaml
aws cloudformation validate-template --template-body file://sg.yaml
```
### SSM Parameter
Create SSM Parameter
```
aws ssm put-parameter --name mySecret --type String --value "hello world!"
```
### S3 Bucket
Create bucket to store child stacks
```
aws s3api create-bucket --bucket cf1554356 --create-bucket-configuration LocationConstraint=us-east-2
```
### Package and Deploy
```
aws cloudformation package --template-file root.yaml --output-template-file packaged.yaml --s3-bucket cf1554356
aws cloudformation deploy --template-file packaged.yaml --stack-name first-stack
```
