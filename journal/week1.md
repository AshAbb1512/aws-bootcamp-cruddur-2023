# Week 1 — App Containerization
## Required Task

## My required task this week included containerizing My application (frontend and backend), making additions to frontend and backend applications and making sure I can run DynamoDB and Postgres containers. Below are the steps I completed for the required task:

## Running frontend and backend locally on Gitpod.

Running frontend and backend locally on Gitpod
To run the backend locally, I copied the commands from the Dockerfile, first installing pip and then running the command for flask. I also had to set the environment variables (frontendurl & backendurl) to * or otherwise, I kept getting 404 error. 

## Run Python

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

