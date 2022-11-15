# basic-web-app

## Description
Using Flask to build a simple rest-api service which exposes a single controller that responses 200 status code on GET requests

## Installation

Install with pip:

```
$ pip install -r requirements.txt
```

## Flask Application Structure 
```
.
├── .github
│   └── workflows
│       └── ci.yml
├── Dockerfile
├── README.md
├── app.py
├── requirements.txt

```

## Run Flask
### Run flask for development
```
$ python app.py
```
In flask, Default port is `5000`

Swagger document page:  `http://127.0.0.1:5000`


### Run with Docker

```
$ docker build -t basic-web-app .

$ docker run -d -p 80:5000 basic-web-app
 
```

### Ci
For each tag that is pushed to the repo, which is in kind `v*.*.*`, a ci build will be run.
In the ci build, the following steps will be running:
- Checkout repository
- Get tag
- Log into registry - login to acr (Azure container registry) using github secrets
- Build & Push - build docker image and push to acr 

### Cd
In order to deploy the new version of the service, the orchestration system should update the image tag to the new version

### References
- [Flask](http://flask.pocoo.org/)
