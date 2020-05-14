## iac-cf-single-instance

aws cloudformation package --template-file root.yaml --output-template-file packaged.yaml --s3-bucket name

aws cloudformation deploy --template-file packaged.yaml --stack-name first-stack
