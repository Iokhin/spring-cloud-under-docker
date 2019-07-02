TO BUILD DOCKER IMAGE: 

    1. cd eureka
    2. docker build -t eureka .
    
TO RUN DOCKER CONTAINER ON PORT 8080:

    1. docker run -d -p 8080:8761 eureka