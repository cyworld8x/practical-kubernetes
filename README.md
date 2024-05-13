Install kubernetes

	choco install kubernetes-cli
	
	kubectl version --client
Enable Hyper-v:
	
	Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All

Install minikube	
	
	choco install minikube

Start minikube
	
	minikube start --driver=virtualbox #/ hyperv

When it fails try to set default by	
	
	docker context use default

Get status
	
	mini status

Open dashvboard
	
	minikube dashboard


To get pods
	
	kubectl get pods
	
To create service
	
	kubectl create service

To get list deployments
	
	kubectl get deployments
	 
To get services
	
	kubectl get services

to expose a pods, type=NodePort, CLusterIP, LoadBalancer

	kubectl expose deployment [deploymentname] --type=LoadBalancer --port 8080

To delete deployment by name, replace "first-app-deployment" by a name

	kubectl delete deployment first-app-deployment

To delete service by name, , replace "first-app-deployment" by a name 

	kubectl delete service first-app-deployment

How to apply Kubernetes deployments using its YAML configuration file:
	
	kubectl apply -f="merged-deployment.yaml"	

How to delete Kubernetes deployments using its YAML configuration file, replace the  merged-deployment.yaml by your file name

	kubectl delete -f merged-deployment.yaml
	
To start see running port by service
	
	minikube service [deploymentname]

To delete deployment by file
	
	kubectl delete -f=[fileapplid]

Before exec yaml on local kubernetes needs to publish an image to docker ub
To login docker hub

	docker login	

To build image from docker compose (replace "phambchungdev/k8s-app" by image name)

	docker image build -t phambchungdev/k8s-app:1.1 .	

To push image (need to login to docker boforehand)

	docker push phambchungdev/k8s-app:1.1

To build app from latest images

	docker run -p 28281:2288 --name nodeapp  phambchungdev/k8s-app

