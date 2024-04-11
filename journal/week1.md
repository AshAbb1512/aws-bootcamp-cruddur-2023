# Week 1 — App Containerization
## Required Task

## My required task this week included containerizing My application (frontend and backend), making additions to frontend and backend applications and making sure I can run DynamoDB and Postgres containers. Below are the steps I completed for the required task:

## Running frontend and backend locally on Gitpod

Running frontend and backend locally on Gitpod
To run the backend locally, I copied the commands from the Dockerfile, first installing pip and then running the command for flask. I also had to set the environment variables (frontendurl & backendurl) to * or otherwise, I kept getting 404 error. 

# Containerize Backend
## Add Dockerfile

## 1st Step: Create a file here: backend-flask/Dockerfile

FROM python:3.10-slim-buster

WORKDIR /backend-flask

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

COPY . .

ENV FLASK_ENV=development

EXPOSE ${PORT}
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]

## Run Flask
## Prepared the python environment in my working directory by installing dependencies, setting environment variables for CORS, running the below command and unlocking the gitpod port:

cd backend-flask

pip3 install -r requirements.txt

export FRONTEND_URL="*"

export BACKEND_URL="*"

python3 -m flask run --host=0.0.0.0 --port=4567
-m mean module

--host=0.0.0.0 binds host to entire ipv4 for easy access

--port=4567 is the port allocated for it to run

make sure to unlock the port on the port tab
open the link for 4567 in your browser
append to the url to /api/activities/home
you should get back json

[image](![Running Frontend and Backend on Gitpod for Adding Docker](https://github.com/Ash01512/aws-bootcamp-cruddur-2023/assets/159699976/13ab21dc-a03c-4dbb-bfb3-70b62f73b7a3)
)


## Building A Docker Running Image = Container
Return to repository root directory
cd ..
Finally built the image with docker build -t flask-backend ./flask-backend from the repository root directory

## Run A Container
##  Use port mapping
Port mapping is a feature in Docker that allows you to 'expose' a specific service running on a particular port of the host machine to a Docker container.Suppose I have a web server running on your host machine on port 4567. To make this service accessible to a Docker container, I can map port 4567 of the host to port 4567 of the container. This is achieved using the following command:

docker run --rm -p 4567:4567 -it backend-flask
A running image is a container so I ran docker container to run the image. 
--rm -p 4567:4567 -d backend-flask 

--rm kills and remove the container once stopped to prevent pile up

-p 4567:4567 specifies port of Host OS binded to port of container

-d mean to run process in detached mode not current terminal


## Get Container Images or Running Container Ids
docker ps
docker images
[image](![Running Frontend and Backend on Gitpod for Adding Docker]([https://github.com/Ash01512/aws-bootcamp-cruddur-2023/assets/159699976/13ab21dc-a03c-4dbb-bfb3-70b62f73b7a3](https://4567-ash01512-awsbootcampcru-sn7ozkl0pfn.ws-us110.gitpod.io/api/activities/home))
)
