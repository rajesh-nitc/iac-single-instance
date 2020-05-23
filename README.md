## iac-single-instance

### validate templates
```
aws cloudformation validate-template --template-body file://root.yaml
aws cloudformation validate-template --template-body file://instance.yaml
aws cloudformation validate-template --template-body file://vpc.yaml
aws cloudformation validate-template --template-body file://sg.yaml
```
### create ssm parameter
```
aws ssm put-parameter --name mySecret --type String --value "hello world!"
```
### create cloudformation bucket to store child stacks
```
aws s3api create-bucket --bucket cf1554356 --create-bucket-configuration LocationConstraint=us-east-2
```
### package and deploy
```
aws cloudformation package --template-file root.yaml --output-template-file packaged.yaml --s3-bucket cf1554356
aws cloudformation deploy --template-file packaged.yaml --stack-name first-stack
```
