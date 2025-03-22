Step 1: Install docker and kubernetes in your virtual machine 
Step 2: Create one directory and simple html page for the web application. THe file added in this repo will display "Hello kubernetes"
Step 3: Dockerize the html web application
        ---> Create the Dockerfile with the contents given in repo in the same directory
        ---> Build the image for the html web appplication using below command 
             **docker build -t <Image-name>**
        ---> After build run the container in local VM and test the application http://localhost:8080
             **docker run -p 8080:80 my-web-app**
        ---> Tag the image and push the docker image to docker hub
              **docker tag <Image-name> <your-dockerhub-username>/<image-name>:latest
              docker push <your-dockerhub-username>/<image-name>:latest**
Step 4: 
        
             
