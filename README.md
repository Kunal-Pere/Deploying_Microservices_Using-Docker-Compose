## A simple microservices application with one service in Python (using Flask) and one service in Java (using Spring Boot). We'll use Docker Compose to deploy both services. Here's the step-by-step guide.


#### Architecture:

The application will consist of two microservices:

Python Microservice: A simple Flask application that provides an API endpoint to return a greeting message.

Java Microservice: A Spring Boot application that provides an API endpoint to return a different greeting message.

Both services will be containerized using Docker and managed using Docker Compose.

#### Directory Structure:

![image](https://github.com/Kunal-Pere/Deploying_Microservices_Using-Docker-Compose/assets/157100045/c6d7d895-0ef7-40de-a5c3-27176ac46d42)

#### Python Microservice:
python-service/app.py

![image](https://github.com/Kunal-Pere/Deploying_Microservices_Using-Docker-Compose/assets/157100045/c1122908-539f-403b-ac03-8dcf449f8e9d)

python-service/requirements.txt

![image](https://github.com/Kunal-Pere/Deploying_Microservices_Using-Docker-Compose/assets/157100045/67afc890-4402-419e-908e-648707d127dc)

python-service/Dockerfile

![image](https://github.com/Kunal-Pere/Deploying_Microservices_Using-Docker-Compose/assets/157100045/aff2cefc-102c-4f58-8cb1-1dd32610f64d)

#### Java Microservice:

java-service/src/main/java/com/example/demo/DemoApplication.java

![image](https://github.com/Kunal-Pere/Deploying_Microservices_Using-Docker-Compose/assets/157100045/fa45e16d-49b8-4786-8ecf-9ceeadcaf603)

java-service/src/main/resources/application.properties

![image](https://github.com/Kunal-Pere/Deploying_Microservices_Using-Docker-Compose/assets/157100045/1c5de912-c8a8-48f3-830f-cb5836aa694c)


java-service/pom.xml

![image](https://github.com/Kunal-Pere/Deploying_Microservices_Using-Docker-Compose/assets/157100045/441e6b61-e744-4711-bc86-759ca3bce97b)
![image](https://github.com/Kunal-Pere/Deploying_Microservices_Using-Docker-Compose/assets/157100045/b52fc9f0-e244-401b-9dd6-9a603b0afdc0)

java-service/Dockerfile

![image](https://github.com/Kunal-Pere/Deploying_Microservices_Using-Docker-Compose/assets/157100045/07522b83-d1a5-4a39-988c-8c8e6f2c79df)

## Docker Compose File

#### docker-compose.yml

![image](https://github.com/Kunal-Pere/Deploying_Microservices_Using-Docker-Compose/assets/157100045/b0cb473b-1067-4483-83ad-b3ff6e0907d3)


### Add the Maven Wrapper to Your Java Project:

    Navigate to your java-service directory.
    Run the following command to generate the Maven Wrapper scripts:

	  mvn -N io.takari:maven:wrapper

### Run the Maven Build:

    Now, you can use the Maven Wrapper to build your project:

	 ./mvnw package

### If you don't have Maven installed, here are the steps to install it:

### On Ubuntu/Debian: 

    sudo apt update
    sudo apt install maven

	  Once your are done with this all stuff Navigate Back to the Root Directory:

	  cd ..

### Start Docker Compose:

   docker-compose up --scale web=3 --build


### Access the Services:

    Python service: Open a browser and go to http://localhost:5000/greet to see the greeting message from the Python service.
    
    Java service: Open a browser and go to http://localhost:8080/greet to see the greeting message from the Java service.

   

### Conclusion:
     In this Project, we created a simple microservices application with one service in Python and another in Java. We used Docker Compose to manage and deploy both services. This setup 
     demonstrates how you can use Docker Compose to orchestrate multi-container applications, making it easier to develop, test, and deploy microservices.   
### Thank You
### Kunal Pere
