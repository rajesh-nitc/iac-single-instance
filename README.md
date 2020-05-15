## iac-cf-single-instance

aws s3api create-bucket --bucket cf1554356 --create-bucket-configuration LocationConstraint=us-east-2

aws cloudformation package --template-file root.yaml --output-template-file packaged.yaml --s3-bucket cf1554356

aws cloudformation deploy --template-file packaged.yaml --stack-name first-stack
