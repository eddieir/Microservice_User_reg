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

https://github.com/eddieir/Microservice_User_reg/blob/master/statucture.txt

You should have the following project structure:


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

