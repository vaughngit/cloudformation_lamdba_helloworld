# Runbook

## Create the Stack
    ```console
aws cloudformation create-stack --stack-name hello-lambda-stack --template-body file://hello_lambda.yml  --capabilities CAPABILITY_NAMED_IAM --profile 
```


## Check status
```console

aws cloudformation list-stacks --query 'StackSummaries[*].[StackName, StackStatus]' --stack-status-filter CREATE_IN_PROGRESS CREATE_COMPLETE --output table --profile 
```

## Invoke the Lambda Function
    aws lambda invoke --invocation-type RequestResponse --function-name HelloLambdaFunction --log-type Tail outputfile.txt;  more outputfile.txt --profile

## Delete the stack
    aws cloudformation delete-stack --stack-name hello-lambda-stack --profile 