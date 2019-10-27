# lambda-sam-hello-world
Lambda SAM hello world

```
export BUCKET=com.atomist.hello

export STACK_NAME=lambda-sam-hello

aws s3 mb s3://$BUCKET

[/Users/rodjohnson/Library/Python/3.7/bin/]sam package --template-file template.yml --s3-bucket $BUCKET --output-template-file packaged-template.yml

sam deploy --template-file packaged-template.yml --stack-name $STACK_NAME --capabilities CAPABILITY_IAM
```

`sam deploy` is an alias for a cloud formation command. See docs. Use `--s3prefix`
It exits without error if no change has been made via a new package call.

```
aws cloudformation describe-stacks
{
    "Stacks": [
        {
            "StackId": "arn:aws:cloudformation:us-east-1:773141716313:stack/simple-hello-world/85214f80-1205-11e9-b634-0e348661d726",
            "DriftInformation": {
                "StackDriftStatus": "NOT_CHECKED"
            },
            "LastUpdatedTime": "2019-01-06T22:50:58.494Z",
            "Tags": [],
            "CreationTime": "2019-01-06T22:50:52.945Z",
            "Capabilities": [
                "CAPABILITY_IAM"
            ],
            "StackName": "simple-hello-world",
            "NotificationARNs": [],
            "StackStatus": "CREATE_COMPLETE",
            "DisableRollback": false,
            "ChangeSetId": "arn:aws:cloudformation:us-east-1:773141716313:changeSet/awscli-cloudformation-package-deploy-1546815052/80b7141e-0a79-4aaa-9aab-df07e2ca0a44",
            "RollbackConfiguration": {}
        }
    ]
}
```
carrot
