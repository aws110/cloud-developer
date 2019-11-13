# Project-3-Microservices
Adam Simonar

##Setting up the Application

###If cloned from github
Be sure to run `npm i` in each of the udacity-c3-[name] folders to successfully
run application.

###Local set up using docker
All of the images used for the application can be found on my docker hub:
1. aws110/reverseproxy
2. aws110/frontend
3. aws110/restapi-user
4. aws110/restapi-feed

Navigate  to the folder containing the docker-compose.yaml file:

Project_3_micro_services/udacity-c3-deployments/docker

Run the compose command to host the application locally:

`docker-compose up`

Go to http://localhost:8100 in a browser to view


###Local set up using a cluster
I chose to use kubeone and terraform to create my kubernetes cluster. The terraform 
configuration files can be found  in the following directory:

Project_3_micro_services/udacity-c3-deployments/terraform/

Once the cluster is running. The files within
 
Project_3_micro_services/udacity-c3-deployments/k8s/[filenames]

must be applied to the cluster using the following command:

`kubectl apply -f [filename]`

Once all files have been successfully applied and the cluster is running, port forward
the frontend and reverseproxy services to host the application locally.

`kubectl port-forward service/frontend 8100:8100`

and

`kubectl port-forward service/reverseproxy 8080:8080`

###CI/CD
Continuous integration and deployment is handled using Travis CI. Whenever an update is
made to my master branch, Travis CI handles the CI and CD to keep the application running.





