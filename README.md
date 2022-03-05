# Containerize-ML-Project-with-Docker
This repository is build as a part of learning process to build and publish ML code as docker image on Azure Container Registery.

The intention of development is to understand the basics of docker, how to work with docker and how to utilize Azure Container Registry for deploying dockerised machine learning project.

# Some basics and intuition of docker.
Docker is basically a cloud computing company and the name of it's product is also Docker. There are lot of containers available in the market and docker is one of them. Enough of JARGAN, I will not go into it's theory you can read other text for that as there are lot of good resources available for that.

As a data scientist we should know why docker? why it does and why it's a HOT POTATO in data science industry? 
I assume you have understanding of code structuring and code modularity (know how to write a ML code using python scripts i.e how to split whole code into various scripts like requirements.txt, train.py, preporocessing.py, predict.py, etc.)

Every ML project has it's dependencies if those dependencies' version don't match sometimes code fail and it happens quite often (trust me). Docker basically allow developers to link code dependencies (requirements.txt) and package it in the form of light weight object (image). So, developer always call this packaged image in the environment of interest (INT or PROD) and as soon as it is called, this image becomes a container which is an isolated environment with the installed dependencies mentioned in requirement.txt file.

**Dockerfile:** This is just a file where we provide instructions to the docker about how to package a machine learning code and what are the dependencies and in what sequence these steps to be ran. So, consider it as just a file for instructions for code packaging.

**Once the Dockerfile is written then just the following commands for packaging your ML code into a docker image.**
%% shell
docker build -t notebook_demo .

