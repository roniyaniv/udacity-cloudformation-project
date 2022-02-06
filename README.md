# In order to setup this CloudFormation stack perform the following steps:

## Change the params jsons to include the needed paramters

- EnvironmentName: choose your own. Must be the same across all params json files 
- KeyName: specify your RSA key
- JumpboxKeyName: specify your RSA key (can be the same as the main KeyName)
- WebAppAMI as well as WebAppInstanceType - define as necessary for the applicaion being run


## Run the following commands in order (make sure the stack is up before running the next command)

```
aws cloudformation create-stack --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" --stack-name <your_stack_name> --template-body file://udagram-network.yml --parameters file://udagram-network-params.json --profile <your_aws_config_profile> --region <relevant_region>

aws cloudformation create-stack --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" --stack-name <your_stack_name> --template-body file://udagram-security.yml --parameters file://udagram-security-params.json --profile <your_aws_config_profile> --region <relevant_region>

aws cloudformation create-stack --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM" --stack-name <your_stack_name> --template-body file://udagram-servers.yml --parameters file://udagram-servers-params.json --profile <your_aws_config_profile> --region <relevant_region>
```
