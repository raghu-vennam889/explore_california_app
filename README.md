Steps Followed:

--> Kubernetes runtime setup :
    - Installed minikube and dependent resources 
--> Containerisation:
     Application is converted into docker image in the following process
    - as it is a web application we need httpd to run it, so in Dockerfile used httpd base image from docker hub and copied application         contents to default path of httpd /usr/local/apache2/htdocs/        
    - with docker build -t <image_name> <path_to_dockerfile>
    - once image is built tested it by running it as on a docker engine installed on my local PC
    - Tagged The inage and pushed it to docker hub
--> Kubernetes Deployment
    - Created Kubernetes manifest file for Deployment of application <Deployment.yaml>
    - Applied kuberneted deploymenyt with the command <kubectl apply -f Deployment.yaml>
--> To expose the app for External Access
     - Used Laodbalancer service to expose the application externally
     - created <service.yaml> file to create Loadbalancer
     - Deployed the service from manifest file
     - Tested accessibility of the application by browsing External_IP of the load balancer service  
