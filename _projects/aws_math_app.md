---
layout: page
title: AWS Serverless Math App
description: Math excercises on AWS
img: assets/img/aws_math/aws_lambda.png
# redirect: https://unsplash.com
importance: 3
category: distributed & cloud
---

<span class="lead"><span class="badge badge-pill badge-primary">AWS SDK</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">AWS CDK</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Serverless</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">FaaS</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Amazon Lambda</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Amazon S3</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Amazon Cognito</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Amazon DynamoDB</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Amazon SNS/SQS</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Localstack</span></span>
<span class="lead"><span class="badge badge-pill badge-primary">Python</span></span>

<span class="lead"><span class="badge badge-pill badge-secondary">Development Period: 10.2022 - 01.2023</span></span>


## Co-authors

Developed this project together with:
- Emir Halilcevic
- Gallus Huber

> Code available upon request.

## Description

We had the opportunity to build a web application leveraging AWS's serverless technologies where we utilized Lambda for computing, Cognito for user management, SNS and SQS for messaging streams, along with S3 and DynamoDB for data storage.

The project served as a practical learning experience in cloud development, where we familiarized ourselves with critical aspects such as deploying applications, selecting appropriate services, and designing, integrating and deploying solutions within the AWS cloud infrastructure.


## Overview

The project contains the implementation of a webapp, which offers the users to solve three different types of excercises (addition, multiplication and derivation). In order to solve these excercises the user _must_ have an account. The user can sign-up and optionally upload a profile picture. The backend is implemented entirely with [AWS CDK](https://aws.amazon.com/cdk/). DynamoDB is used to store the excercises and Cognito is used for User management, authentication and authorization. During development the AWS stack was deployed to a [Localstack](https://localstack.cloud/) instance running in a docker container.

## Architecture

The complete architecutre of the AWS Stack is presented in the following diagram:
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/aws_math/architecture.png" title="Implementation Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Architecture of the solution.
</div>

## Components

- AWS Stack:
  - DynamoDB
  - Cognito
  - S3
  - SNS
  - SQS
  - ApiGateway
  - Lambda
- Frontend:
  - Vue.js application

## How to run

Prerequisite: Docker already installed and Docker Daemon is running

### Linux/Mac

```shell
$ make startAll
```

### Windows

Prerequisite:
- `make` is installed (e.g. via [`chocolatey`](https://chocolatey.org/) or Cygwin):

Run:
```shell
$ make startAll
```

**Note** - if Windows line endings are added automatically on pull, execute: `sed -i -e 's/\r$//' ./entrypoint.sh` in Git/UbuntuWSL bash in the root directory. 

## How to test

Prerequisites:

- AWS CLI Version 2
    - https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
- Python
    - https://www.python.org/downloads/
- pytest
    - pip install pytest

```shell
$ make start
$ make test
$ make stop
```

## Logs

Logs:<br />

```shell
$ aws --endpoint-url=http://localhost:4566/ logs describe-log-groups
$ aws --endpoint-url=http://localhost:4566/ logs tail <log-group-name> --follow
```

### Extra feature: Windows Terminal

If [`Windows Terminal`](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701) app is installed, one can run the `./util/start_lambda_logs_win_terminal.py` to start the Cognito related lambdas, Excercise Evaluator and Generator lambdas, Watcher and post_solution lambda in two windows, four panes each and observe the behavior of the main code segments.
