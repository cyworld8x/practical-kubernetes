Install kubernetes
- choco install kubernetes-cli
- kubectl version --client
Enable Hyper-v:
	Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All
Install minikube	
	choco install minikube
Start minikube
	
	minikube start --driver=virtualbox / hyperv
When it fails try to set default by	
	docker context use default

Get status
	mini status
Open dashvboard
	minikube dashboard
To apply deployment.yaml
	kubectl apply -f="deployment.yaml"

To get pods
	kubectl get pods
To start deployment
	kubectl get deployments
	
To create service
	kubectl create service
To get list deployments
	 kubectl get deployments
	 
To get services
	kubectl get services

to expose a pods, type=NodePort, CLusterIP, LoadBalancer

	kubectl expose deployment [deploymentname] --type=LoadBalancer --port 8080
	
To start see where pods is creating
	minikube service [deploymentname]
To delete deployment by file
	kubectl delete -f=[fileapplid]

