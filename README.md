# Containerize-ML-Project-with-Docker
This repository is build as a part of learning process to build and publish ML code as docker image on Azure Container Registery.

The intention of development is to understand the basics of docker, how to work with docker and how to utilize Azure Container Registry for deploying dockerised machine learning project.

# Some basics and intuition of docker.
Docker is basically a cloud computing company and the name of it's product is also Docker. There are lot of containers available in the market and docker is one of them. Enough of JARGAN, I will not go into it's theory you can read other text for that as there are lot of good resources available for that.

As a data scientist we should know why docker? why it does and why it's a HOT POTATO in data science industry? 
I assume you have understanding of code structuring and code modularity (know how to write a ML code using python scripts i.e how to split whole code into various scripts like requirements.txt, train.py, preporocessing.py, predict.py, etc.)

Every ML project has it's dependencies if those dependencies' version don't match sometimes code fail and it happens quite often (trust me). Docker basically allow developers to link code dependencies (requirements.txt) and package it in the form of light weight object (image). So, developer always call this packaged image in the environment of interest (INT or PROD) and as soon as it is called, this image becomes a container which is an isolated environment with the installed dependencies mentioned in requirement.txt file.

**Dockerfile:** This is just a file where we provide instructions to the docker about how to package a machine learning code and what are the dependencies and in what sequence these steps to be ran. So, consider it as just a file for instructions for code packaging. Pu this is Dockerfile in the active directory of your ML code without any extension (don't put these and their relatives .txt, .csv, .json)

**Once the Dockerfile is written then just the following commands for packaging your ML code into a docker image.**
Open command prompt and go to the working directory of your ML code and the run the commands below.

```
docker build -t MLCodeImage .
```
Remember dot (.) at the end, it means take code from the active directory and build it's image with tag "MLCodeImage" and put in the base directory of docker container registry (space where you can save/keep your docker images)

Retrieve built image
```
docker images
```
You would be able to see image with tag "MLCodeImage"

# Concept Alert:
*Docker Hub* It's a container registry where docker can save your images but it is publically available for free users and accessible to everyone on internet. So for this we use
Azure Container Registry to save our images and for enterprise ML deployment we either use AWS (Elastic Container Registry) or Azure (Azure Container Registry). So both of them are just a vault where you can keep your images safe. Also during deployment the inference script (script for prediction in production) utilizes these docker images so these container registries are also needed so that we can work on cloud as well and run the container on Virtual Machines.

# Bonus Alert:
How to deploy on Kubernetes? Kubernetes is just a manager which manages the proper running of containers.
*Kubectl is just a command line interface so that developers could interact with Kubernetes clusters, nodes and podes. Nothing more. So don't worry much.
Very high level roadmap but it will helps to understand overall workflow.

Step-1: Save docker image to ACR or AWS-ECR
Step-2: Establish connection between container registry and Kubernetes (Ofcourse you have to allocate Kubernetes and Container registry first)

I HAVE GOT SOME WORK. LET'S COMPLETE IT LATER.
In the mean time you can explore next steps.
