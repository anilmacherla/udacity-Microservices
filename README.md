
Summary : 

This project goal is to operationalize microservices in this case machine learning microservice using kubernetes, which is an open-source system for automating the management of containerized applications.This will showcase the abilities to operationalize production microservices.

Info about the files : 

This repo contains files to containerise the application and deploy it. and also files to deploy using kubernetes and thier respective loggings are saved in docker_out.txt and kubernetes_output.txt. and also .circleci for testing purposes.
1)app.py: This is the flask app that runs the service
2)Makefile: This file has make commands that allows for easy setup of a project
3)Dockerfile: This file has the setup for creating a Docker image for the microservice
4)run_docker.sh: This script creates a docker image from the Dockerfile, list the images and starts     a container
5)make_prediction.sh: This script sends data for prediction using curl and prints the predicted value on the command line
6)upload_docker.sh: This script uploads a docker image to docker hub
7)run_kubernetes.sh: This script runs the docker image in a kubernetes cluster
8)docker_out.txt : logs related to docker are saved in this
9)kubernetes_output.txt " logs related to kubernetes are saved in this


Instructions: 

1) Clone this repo
 `git clone https://github.com/duoarc/Rent-Prediction-App-Containerisation-Deployment.git`

2) Install [python](https://www.python.org/) if not already installed and run this command to create a virtual environment and activate it
`make setup`

3) Install the project dependencies
`make install`

4) Run this command to lint the project files
`make lint`

5) Run this script to build a docker image for the app and start the app in a docker container:
`./run_docker.sh`

6)Run this script to get a prediction from the app running in the Docker container:

`./make_prediction.sh`

7) Run this script to upload the docker image to your Docker hub account. Note you'll have to edit the script and change the Docker ID to yours:

`./upload_docker.sh`

8) Run this script to run the service in a kubernetes cluster. You'll be making use of my image repo. You can edit the script and change to your image repo on Docker hub if you've built and pushed your image. This script will be run twice to activate the port forwarding. Give some minutes after first run so that the pod can be up and running before attempting port forwarding:
`./run_kubernetes.sh`

9) Run this script to get a prediction from the app running in the Kubernetes Cluster after port forwarding is successful:
`./make_prediction.sh `
