# Overview
Provide a docker image for jenkins workers to build Java projects.

# Create repository in ECR
Run the following to create a new repository in ECR for your new image:

```
aws cloudformation create-stack \
    --stack-name jenkins-worker-java8-repo \
    --template-body file://cfn/repo.template
```

# Login to new repository
Run the following to login to ECR:

```
$(aws ecr get-login)
```

# Create docker image
Run the following to build a new image:

```
docker build -t 324320755747.dkr.ecr.us-west-2.amazonaws.com/jenkins-worker-java8 .
```

# Push docker image
Run the following to push the image to the ECR repo:

```
docker push 324320755747.dkr.ecr.us-west-2.amazonaws.com/jenkins-worker-java8
```
