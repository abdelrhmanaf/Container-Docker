# Running a Java-based Web Application on EC2 Instance using Docker

This guide describes the steps for running a Java-based web application on an EC2 instance using Docker with the provided Dockerfiles and Docker Compose file.

## Prerequisites

- An EC2 instance
- Docker and Docker Compose installed on the EC2 instance
- JDK 8 and Maven installed on the EC2 instance

## Step 1: Install JDK 8 and Maven

Install JDK 8 and Maven by running the following commands:

```
sudo apt update
sudo apt install -y openjdk-8-jdk maven
```

## Step 2: Clone the repository

Clone the repository containing the Dockerfiles and Docker Compose file to the EC2 instance:


## Step 3: Build the Java-based web application artifact

Change to the directory containing the Java-based web application source code and build the application artifact using Maven:

```
cd Container-Docker
mvn install
```

This will build the Java-based web application artifact and store it in the `target` directory.

## Step 4: Pull the required Docker images

Pull the required Docker images from Docker Hub:

```
docker pull memcached
docker pull rabbitmq
```

## Step 5: Build the Docker images

Change to the directory containing the Dockerfiles and build the Docker images:

```
cd <repository_name>
docker build -t abdelrhmanaf/app:V1 -f Dockerfile.app .
docker build -t abdelrhmanaf/db:V1 -f Dockerfile.db .
docker build -t abdelrhmanaf/web:V1 -f Dockerfile.web .
```

## Step 6: Start the Docker containers

Start the Docker containers using the Docker Compose file:

```
docker-compose up -d
```

This will start the containers for the database, Memcached, RabbitMQ, web application, and Nginx.

## Step 7: Access the web application

To access the web application, open a web browser and navigate to the public IP address of the EC2 instance on port 80. You should see the web application running.

## Step 8: Stop the Docker containers

To stop the Docker containers, run the following command:

```
docker-compose down
```

This will stop and remove the containers.

## Conclusion

By following these steps, you should now be able to run the Java-based web application on an EC2 instance using Docker with the provided Dockerfiles and Docker Compose file, with Memcached and RabbitMQ containers also running. Before building the Docker images, the Java-based web application artifact is built using Maven and stored in the `target` directory.
