[![CircleCI](https://dl.circleci.com/status-badge/img/circleci/9TTfYQV8JrW1WjtqSrz2jr/Uceu3SLDHgcU7YvWRHwfEY/tree/main.svg?style=svg&circle-token=1fbd54a5fb61f0bd383749ff15538b7b76f54a9c)](https://dl.circleci.com/status-badge/redirect/circleci/9TTfYQV8JrW1WjtqSrz2jr/Uceu3SLDHgcU7YvWRHwfEY/tree/main)

# Operationalize-a-Machine-Learning-Microservice-API

## Project Summary
Microservice Project [Udacity Cloud DevOps Engineer Nanodegree]

This project consisted of creating a dockerized machine learning microservice application and then deploying it into a kubernetes cluster. Along the way, the project required Makefile configurations to simplify the environment setup and dependency installation. Upon deplying the docker container, a live prediction was executed to test the status of the deployed microservice.


### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

### File Explanations
* /.circleci : config.yml file for running CI/CD
* /model_data : ML data for prediction
* /output_txt_files : Docker and Kubernetes log outputs from microservice prediction
* Dockerfile : Dockerfile for building the image 
* Makefile : Setup, installation, and linting commands
* app.py : Python flask app that predicts housing prices
* make_prediction.sh : Script for requesting prediction from python flask application 
* requirements.txt : List of dependency installs
* run_docker.sh : Script that executes a local docker image run
* run_kubernetes.sh : Script that executes the deployment of the container in kubernetes locally
* upload_docker.sh : Script for uploading docker image to dockerhub

---

## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
    - Install Docker
    - Lint check with hadolint and pylint
    - Install minikube/kubectl
* Setup and Configure Kubernetes locally
    - minikube start
* Create Flask app in Container
    - run run_docker.sh
* Run via kubectl
    - run run_kubernetes.sh
