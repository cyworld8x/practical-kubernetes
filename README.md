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
	
	minikube status

Open dashboard
	
	minikube dashboard

To delete installed driver
	
	minikube delete

To get pods
	
	kubectl get pods

To delete a pod 

	kubectl delete -n default pod [podname]

To open service/pod outside cluster by using port-forward like

	 kubectl port-forward user-app-deployement-6d878c8d66-f72tq 8080:8080
	 kubectl port-forward service/user-app-service 8080:8080
	
To create service
	
	kubectl create service

To get list deployments
	
	kubectl get deployments
	 
To get services
	
	kubectl get services

To get logs of pod 

	kubectl logs [pod name] 

To expose a pods, type=NodePort, CLusterIP, LoadBalancer

	kubectl expose deployment [deploymentname] --type=LoadBalancer --port 8080

To delete deployment by name, replace "first-app-deployment" by a name

	kubectl delete deployment first-app-deployment

To delete service by name, , replace "first-app-deployment" by a name 

	kubectl delete service first-app-deployment

How to apply Kubernetes deployments using its YAML configuration file:
	
	kubectl apply -f="merged-deployment.yaml"	

How to delete Kubernetes deployments using its YAML configuration file, replace the  merged-deployment.yaml by your file name

	kubectl delete -f merged-deployment.yaml
	
To see running port by service
	
	minikube service [deploymentname]

To let kubectl pick a local port forward

	kubectl port-forward [servicename] [LISTEN_PORT]:[DEST_PORT]

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


PersistentVolume (PV) is a piece of storage in the cluster that has been provisioned by an administrator. It is a resource in the cluster that has a lifecycle independent of any individual pod that uses the PV. PVs are volume plugins like Volumes, but have a lifecycle independent of any individual pod that uses the PV.

PersistentVolumeClaim (PVC) is a request for and claim to a PersistentVolume resource. PVCs are used by users to request storage with a specific size, access mode, and StorageClass for the PersistentVolume. If a PersistentVolume that satisfies the request exists or can be provisioned, the PersistentVolumeClaim is bound to that PersistentVolume.

