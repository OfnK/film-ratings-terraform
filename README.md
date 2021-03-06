# Film Ratings Terraform

This repo has the terraform definitions to set up an AWS cluster for the "Film Ratings app" from Chris Howe-Jones' [blog](https://circleci.com/blog/deploy-a-clojure-web-application-to-aws-using-terraform/)

## Prerequisites

Install Terraform. This repo as been tested on version v0.12.2

Which Terraform do I have?

``` shell
 terraform -version 
``` 

Set up an AWS account and add a new IAM user with admin
privilege. Generate a new key pair for that user called
`film_ratings_key_pair`. Copy the `film_ratings_key_pair.pem` to your
`~/.ssh` directory and set the permissions like so: `chmod 400
~/.ssh/film_ratings_key_pair.pem`.

## Initialise Terraform

Change directory to the project directory you cloned this to. Then
run:

``` shell
terraform init
```
## Setup required Environment vars

These Terraform resources require the following variables to be typed
in on every run and will prompt for them:

```
aws_access_key_id
aws_secret_access_key
```

If you tire of typing these in you can set the following environment
variables to the appropriate values:

``` shell
export TF_VAR_aws_access_key_id=xxxxxxxx
export TF_VAR_aws_secret_access_key=xxxxxxxxxxxxxxxxxxx
```

## Check what will be created

To check what will be created using these Terraform resources, run:

``` shell
terrform plan
...
```

## To apply the changes to AWS

To apply the changes to your AWS account:

``` shell
terraform apply
...
```

## To destroy resources in AWS

To destroy the resources in your AWS account:

``` shell
terraform destroy

```

## Legal

Copyright © 2019 Chris Howe-Jones
