# SageMaker Deploy With StepFunctions
Step Functions for managing the deployment of SageMaker endpoints.

## How to use
Create a new state machine with the contents of `definition.json` .

## Execution
When executing, enter the required variables according to the contents of `execution_input.json` .  
  
- `ECRPath` : URI of the container image used in the model
- `ModelPath` : S3 path of model file (ex. `models.tar.gz` )
- `ModelName` : SageMaker model name
- `EndpointName` : SageMaker endpoint name
- `EndpointConfigNameCanary` : The name of the SageMaker endpoint config to use when canary release
- `EndpointConfigName` : The name of the final SageMaker endpoint config to release
- `ExecutionRoleArn` : ARN of IAM role to use when running SageMaker endpoint
- `SecurityGroupIds` : List of security group IDs used in SageMaker endpoint
- `Subnets` : List of subnet IDs used in SageMaker endpoint
- `InstanceCount` : Number of instances to run
- `InstanceType` : Instance type to run
- `MinCapacity` : Minimum number of autoscale capacities
- `MaxCapacity` : Maximum number of autoscale capacities
- `TargetValue` : Autoscale threshold (number of requests per minute per instance)

## Note
Read the official docs for a detailed description of the variables.  
  
- https://docs.aws.amazon.com/sagemaker/latest/APIReference/Welcome.html
- https://docs.aws.amazon.com/autoscaling/application/APIReference/Welcome.html
