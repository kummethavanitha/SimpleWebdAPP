Step 1: Install docker and kubernetes in your virtual machine 


![docker & k8s installation](https://github.com/kummethavanitha/SimpleWebdAPP/blob/194ce4535d7c10cd1c1fedbf50d899831eb8863b/Docker%26kubernetes%20installation.PNG)


Step 2: Create one directory and simple html page for the web application. THe file added in this repo will display "Hello kubernetes"


        ---> mkdir simplewebapp

        
        ---> cd simplewebapp

        
        ---> vi index.html



![docker & k8s installation](https://github.com/kummethavanitha/SimpleWebdAPP/blob/194ce4535d7c10cd1c1fedbf50d899831eb8863b/Directory%26files.PNG)

Step 3: Dockerize the html web application


        ---> Create the Dockerfile with the contents given in repo in the same directory
             vi Dockerfile 

             
        ---> Build the image for the html web appplication using below command 
             **docker build -t <Image-name>**


![docker & k8s installation](https://github.com/kummethavanitha/SimpleWebdAPP/blob/a70ba5b78b1c042fc38b16232ed122cdf71baa67/docker-build.PNG)

             
        ---> After build, run the container in local VM and test the application http://localhost:8080
             **docker run -p 8080:80 my-web-app**


![docker & k8s installation](https://github.com/kummethavanitha/SimpleWebdAPP/blob/a70ba5b78b1c042fc38b16232ed122cdf71baa67/docker-run.PNG)


![docker & k8s installation](https://github.com/kummethavanitha/SimpleWebdAPP/blob/a70ba5b78b1c042fc38b16232ed122cdf71baa67/docker-out.PNG)
             
        ---> Tag the image and push the docker image to docker hub
             **docker tag <Image-name> <your-dockerhub-username>/<image-name>:latest**
             **docker push <your-dockerhub-username>/<image-name>:latest**

![docker & k8s installation](https://github.com/kummethavanitha/SimpleWebdAPP/blob/a70ba5b78b1c042fc38b16232ed122cdf71baa67/docker-push.PNG)


Step 4: Deploy Your container image to Kubernetes


        ---> Create a Kubernetes Deployment and Service YAML file and apply to the cluster
             vi deploy.yaml and vi svc.yaml
             **kubectl apply -f deploy.yaml**
             **kubectl apply -f deploy.yaml**

             
        ---> Check the status of  pod and svc:
             **kubectl get pods**
             **kubectl get service**


![docker & k8s installation](https://github.com/kummethavanitha/SimpleWebdAPP/blob/a70ba5b78b1c042fc38b16232ed122cdf71baa67/k8s-deploy.PNG)


Step 5: Access Your Application


        ---> Open the browser in your local machine and check the application using http://<internal-node-ip>:<port-no>
       
        
        Note: check the port number in svc.yaml file 


 ![docker & k8s installation](https://github.com/kummethavanitha/SimpleWebdAPP/blob/a70ba5b78b1c042fc38b16232ed122cdf71baa67/k8s-out.PNG)
        
             
