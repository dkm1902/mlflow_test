# mlflow_test

## For Dagshub:

MLFLOW_TRACKING_URI=https://dagshub.com/dkm1902/mlflow_test.mlflow \
MLFLOW_TRACKING_USERNAME=dkm1902 \
MLFLOW_TRACKING_PASSWORD=bb6144e355b78cef904145078cc8cabbb54e0536 \
python script.py

```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/dkm1902/mlflow_test.mlflow

export MLFLOW_TRACKING_USERNAME=dkm1902

export MLFLOW_TRACKING_PASSWORD=bb6144e355b78cef904145078cc8cabbb54e0536

```

## MLflow on AWS Setup:
1. Login to AWS console.
2. Create IAM user with AdministratorAcess
3. Export the credentials in your AWS CLI by running "aws configure"
4. Create a s3 bucket
5. Create EC2 machine (Ubuntu) & add Security groups 5000 port

Run the following command on EC2 machine
```bash
sudo apt update

sudo apt install python3-pip

sudo pip3 install pipenv

sudo pip3 install virtualenv

mkdir mlflow

cd mlflow

pipenv install mlflow

pipenv install awscli

pipenv install boto3

pipenv shell

## Then set aws credentials
aws configure

#Finally
mlflow server -h 0.0.0.0 --default-artifact-root s3://mlflow-buc12

#open Public IPv4 DNS to the port 5000


#set uri in your local terminal and in your code
export MLFLOW_TRACKING_URI=""

```