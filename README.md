
#  Web application deploy into Kubernetes cluster

Understanding Kubernetes:

Kubernetes, often abbreviated as K8s, is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications.

It abstracts the underlying infrastructure and provides a unified API to manage clusters of containers effectively. With Kubernetes, developers can focus on building applications without worrying about the complexities of deployment and scaling.

## Steps
#### Step 1. Create ec2 instance and installations
Use name as you preferd i used Netflix-server 

Type is (AMI- Ubuntu 22.04, Type- t2.medium)

Install updates. (sudo apt-get update)

Install Docker. [Docker installation doumentaion](https://docs.docker.com/engine/install/ubuntu/)

Give permission to Docker (sudo usermod -aG docker $USER && newgrp docker)

Minikube and Kubectl installation Install Docker. [Minikube installation doumentaion](https://www.linuxtechi.com/how-to-install-minikube-on-ubuntu/)

`sudo docker --version`

`sudo minikube version`

`sudo Kubectl version`

#### Step 1. Clone the repository to ec2
```
git clone https://github.com/NirmalNaveen20/netflix-k8.git
```

#### Step 2. Create a image and push to the docker hub

```
sudo docker build -t nteflix-app .
```

`sudo docker login`

Provide your docker hub credentials 

Push image to the docker hub

`sudo docker push <your docker hub username/netflix-app>`

#### Step 3. Create Deployment.yml and Service.yml files for Deployments
```
sudo kubectl apply -f deployment.yml
```

```
sudo kubectl apply -f service.yml
```

#### Step 4. Get the URL and curl it to check the website accessibility.

```
sudo minikube service netflix-app --url 
```

check accessibility

`curl -L <minikube-address>`

Check with Public URL and we can now see the Netflix APP running on the server.

## Author

- [@Nirmal Naveen](https://www.nirmalnaveen.com/)

![Logo](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTlPjhPV6D68kBoBq82reUr6ndqcI_n9YPSQ9WA3sqT_RAXpDVcujzTO1MmWrcmcGYeyA&usqp=CAU)


