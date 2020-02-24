This repo is dedicated to the user registration microservice which designed with python flask. In order to run this project on you local you need to fllow these there steps:

Step A:  This project requires

    Docker 18.06.1-ce
    Docker Compose 1.22.0
    Docker Machine 0.15.0 (Optional)
    PC, Mac or Linux
    Git 2.15.1

Step B: Microservices installation
This is a a guide to install all of the Microservices
Project setup

Create the following project structure

$ mkdir code
$ cd code
$ git clone git@github.com:PacktPublishing/Hands-on-Microservices-with-Python.git frontend.git
$ git clone git@github.com:PacktPublishing/Hands-on-Microservices-with-Python-User-Service.git user_service.git
$ git clone git@github.com:PacktPublishing/Hands-on-Microservices-with-Python-Product-Service.git product_service.git
$ git clone git@github.com:PacktPublishing/Hands-on-Microservices-with-Python-Order-Service.git order_service.git

You should have the following project structure:

├── app
│   ├── app.py
│   ├── frontend
│   │   ├── api
│   │   │   ├── __init__.py
│   │   │   ├── OrderClient.py
│   │   │   ├── ProductClient.py
│   │   │   ├── __pycache__
│   │   │   │   ├── __init__.cpython-38.pyc
│   │   │   │   ├── OrderClient.cpython-38.pyc
│   │   │   │   ├── ProductClient.cpython-38.pyc
│   │   │   │   └── UserClient.cpython-38.pyc
│   │   │   └── UserClient.py
│   │   ├── forms.py
│   │   ├── __init__.py
│   │   ├── __pycache__
│   │   │   ├── forms.cpython-38.pyc
│   │   │   ├── __init__.cpython-38.pyc
│   │   │   └── routes.cpython-38.pyc
│   │   ├── routes.py
│   │   └── templates
│   │       ├── base_col_1.html
│   │       ├── base_col_2.html
│   │       ├── base.html
│   │       ├── home
│   │       │   └── index.html
│   │       ├── login
│   │       │   └── index.html
│   │       ├── macros
│   │       │   ├── _macros_basket.html
│   │       │   └── _macros_form.html
│   │       ├── _messages.html
│   │       ├── nav_header.html
│   │       ├── order
│   │       │   └── thankyou.html
│   │       ├── product
│   │       │   └── index.html
│   │       └── register
│   │           └── index.html
│   ├── home
│   │   └── __pycache__
│   │       ├── forms.cpython-36.pyc
│   │       ├── __init__.cpython-36.pyc
│   │       └── routes.cpython-36.pyc
│   ├── __init__.py
│   ├── requirements.txt
│   ├── static
│   │   ├── css
│   │   │   └── main.css
│   │   └── images
│   │       ├── apple.png
│   │       ├── banana.png
│   │       ├── book-red.png
│   │       ├── coffee.png
│   │       ├── fidget-spinner-2399715_960_720.png
│   │       ├── Fidget_spinner_in_blue.png
│   │       ├── fidget-spinner-yellow.png
│   │       ├── rubber_duck.png
│   │       └── tomato.png
│   └── user
│       └── __pycache__
│           ├── __init__.cpython-36.pyc
│           └── routes.cpython-36.pyc
├── bin
├── docker-compose.deploy.yml
├── docker-compose.yml
├── Dockerfile
├── docs
│   ├── api
│   │   └── postman
│   │       ├── order-system.postman_collection.json
│   │       └── Packt Order Management - Dev.postman_environment.json
│   └── install
│       ├── frontend.md
│       ├── microservices.md
│       └── requirements.md
├── LICENSE
├── __pycache__
│   ├── HelloMicroService.cpython-36.pyc
│   └── service.cpython-36.pyc
├── README.md
└── tests
    └── test_pages.py

Docker Machine (optional)

Create a Docker machine for the project

$ docker-machine create packt-order-management

Start the machine

$ docker-machine start packt-order-management

Update the shell

$ docker-machine env packt-order-management
$ eval $(docker-machine env packt-order-management)

Get the IP of the machine

$ docker-machine ip packt-order-management
192.168.1.131

Docker Compose

Install the containers. Run the following commands from inside the frontend.git folder.

$ docker-compose -f docker-compose.deploy.yml up -d

Check that all the containers are running

$ docker-compose ps 

  Name                        Command               State          Ports        
---------------------------------------------------------------------------------------
microservice_frontend_1   /bin/sh -c python app.py r ...   Up      0.0.0.0:81->5000/tcp

Product database

To add products into the product database please follow this guide
Run the application

Go to the IP address in a web browser. If you are using Docker Machine then the IP will be the IP of the machine. If you are not using Docker machine the IP will be your local host
To rebuild the Docker images and recreate the containers

$ docker-compose -f docker-compose.deploy.yml build

Then run the following to recreate the containers

$ docker-compose -f docker-compose.deploy.yml up -d

