# repostatus-gh-demo

This is a sample application that pulls some basic information from GitHub repositories and caches
that data in DynamoDB.

## AWS App Runner

### Create DynamoDB table & configure access

To allow our app to function properly, we need a DynamoDB table, and grant AWS App Runner access.

```shell
$ aws cloudformation deploy \
  --stack-name $(basename $(pwd))-infra \
  --template-file hack/apprunner-prereqs-cfn.yaml \
  --capabilities CAPABILITY_IAM
```
### Cloudformation Template
```
cat ~/environment/repostatus-gh-demo/hack/apprunner-prereqs-cfn.yaml
```

### Deploy Template
```
cd ~/environment/repostatus-gh-demo && aws cloudformation deploy \
  --stack-name repostatus-gh-demo-infra \
  --template-file hack/apprunner-prereqs-cfn.yaml \
  --capabilities CAPABILITY_IAM
```

