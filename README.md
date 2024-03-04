# MLFLOW-Implementation



## For Dagshub:

MLFLOW_TRACKING_URI=https://dagshub.com/AcheampongStephen/MLFLOW-Implementation.mlflow \
MLFLOW_TRACKING_USERNAME=AcheampongStephen \
MLFLOW_TRACKING_PASSWORD=9b7471a68fbc760387135ad6eb899bde0456a4f0 \
python script.py


```bash
export MLFLOW_TRACKING_URI=https://dagshub.com/AcheampongStephen/MLFLOW-Implementation.mlflow
export MLFLOW_TRACKING_USERNAME=AcheampongStephen
export MLFLOW_TRACKING_PASSWORD=9b7471a68fbc760387135ad6eb899bde0456a4f0
```


## MLFlow on AWS
1. Login to AWS consloe
2. Creat IAM user with AdminstrativeAccess
3. Export the credentials in your AWS CLI by running:
```
aws configure
```
4. Create s3 bucket
5. Create EC2 machine (Ubuntu) & add security groups 5000 port

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

## The set aws crednetials
aws configure

# Finally
mlflow server -h 0.0.0.0 --default-artifact-root s3://mlflow-buc26

#open Public IPV4 DNS to port 5000

# set uri in your local terminal and in your code
export MLFLOW_TRACKING_URI=http://ec2-3-19-54-19.us-east-2.compute.amazonaws.com:5000/
```