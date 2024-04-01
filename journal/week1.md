# Week 1 — App Containerization
## Required Task

## My required task this week included containerizing My application (frontend and backend), making additions to frontend and backend applications and making sure I can run DynamoDB and Postgres containers. Below are the steps I completed for the required task:

## Running frontend and backend locally on Gitpod

Running frontend and backend locally on Gitpod
To run the backend locally, I copied the commands from the Dockerfile, first installing pip and then running the command for flask. I also had to set the environment variables (frontendurl & backendurl) to * or otherwise, I kept getting 404 error. 

# Containerize Backend

## Run Flask

cd backend-flask

pip3 install -r requirements.txt

export FRONTEND_URL="*"

export BACKEND_URL="*"

python3 -m flask run --host=0.0.0.0 --port=4567

cd ..


make sure to unlock the port on the port tab
open the link for 4567 in your browser
append to the url to /api/activities/home
you should get back json

[image](![Running Frontend and Backend on Gitpod for Adding Docker](https://github.com/Ash01512/aws-bootcamp-cruddur-2023/assets/159699976/13ab21dc-a03c-4dbb-bfb3-70b62f73b7a3)
)

## Add Dockerfile

## Create a file here: backend-flask/Dockerfile

FROM python:3.10-slim-buster

WORKDIR /backend-flask

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

COPY . .

ENV FLASK_ENV=development

EXPOSE ${PORT}
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]

## Building A Docker Container


docker build -t  backend-flask ./backend-flask

## Run A Container
##  Use port mapping
Port mapping is a feature in Docker that allows you to 'expose' a specific service running on a particular port of the host machine to a Docker container.Suppose I have a web server running on your host machine on port 4567. To make this service accessible to a Docker container, I can map port 4567 of the host to port 4567 of the container. This is achieved using the following command:

docker run --rm -p 4567:4567 -it backend-flask

