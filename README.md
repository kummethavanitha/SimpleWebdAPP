Step 1: Install docker and kubernetes in your virtual machine 


Step 2: Create one directory and simple html page for the web application. THe file added in this repo will display "Hello kubernetes"


        ---> mkdir simplewebapp

        
        ---> cd simplewebapp

        
        ---> vi index.html


Step 3: Dockerize the html web application


        ---> Create the Dockerfile with the contents given in repo in the same directory
             vi Dockerfile 

             
        ---> Build the image for the html web appplication using below command 
             **docker build -t <Image-name>**

             
        ---> After build run the container in local VM and test the application http://localhost:8080
             **docker run -p 8080:80 my-web-app**

             
        ---> Tag the image and push the docker image to docker hub
             **docker tag <Image-name> <your-dockerhub-username>/<image-name>:latest**
             **docker push <your-dockerhub-username>/<image-name>:latest**


Step 4: Deploy Your container image to Kubernetes


        ---> Create a Kubernetes Deployment and Service YAML file and apply to the cluster
             vi deploy.yaml and vi svc.yaml
             **kubectl apply -f deploy.yaml**
             **kubectl apply -f deploy.yaml**

             
        ---> Check the status of  pod and svc:
             **kubectl get pods**
             **kubectl get service**


Step 5: Access Your Application


        ---> Open the browser in your local machine and check the application using http://<internal-node-ip>:<port-no>
       
        
        Note: check the port number in svc.yaml file 
        
             
