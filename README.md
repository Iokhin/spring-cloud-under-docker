EUREKA UNDER DOCKER
    
    TO BUILD EUREKA DOCKER IMAGE: 
    
        1. cd eureka
        2. docker build -t eureka .
        
    TO RUN EUREKA DOCKER CONTAINER ON PORT 8080:
    
        1. docker run -d -p 8080:8761 eureka
        
POSTGRES UNDER DOCKER

    TO BUILD POSTGRES DOCKER IMAGE: 
        
            1. cd docker-postgresql
            2. docker build -t frodenas/postgresql:9.6 .
            
    TO RUN POSTGRES DOCKER CONTAINER ON PORT 5432:
    
        1.docker run -d \
              --name postgresql \
              -p 5432:5432 \
              -e POSTGRES_USERNAME=myuser \
              -e POSTGRES_PASSWORD=mypassword \
              frodenas/postgresql