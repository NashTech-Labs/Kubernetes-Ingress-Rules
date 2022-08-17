# Kubernetes-Ingress-Rules
 By creating ingress rules you can access your applications through domain name instead of accessing them through IP addresses and ports
PREREQUISITES FOR THIS
- Kubernetes Cluster
- Kubectl connect

What is Ingress?
Ingress is an API object that allows the external traffic to the Kubernetes cluster based on the routing mechanism. It provides routing rules to manage external users’ access in a Kubernetes cluster via HTTP/HTTPS.

Enable nginx ingress controller
- minikube addons enable ingress

check the namespaces
- kubectl get namespaces (here, you will see "ingress-nginx")

Check pods inside this namespace
- kubectl get pods -n ingress-nginx

Now deploy a Hello World application using "ingress-deployment.yaml" file

Apply this manifest file
- kubectl apply -f [file-name]

Now, check the status of deployments, pods and replicaset
- kubectl get deployments
- kubectl get pods
- kubectl get replicaset

Expose this deployment
- kubectl expose deployment [deployment-name] --type=NodePort --port=8080

Verify the service
- kubectl get service

Now, access your application via the node ip and the node port

To check the node ip
- kubectl get nodes -o wide [copy the internal-ip]

Open the browser and type node ip and node port(given in service)
[192.168.49.2:31900] like this

Now, create "ingress.yaml" file, apply this file

And then, do the verification
- kubectl get ingress [the address field should take couple of minutes]

Add the hosts and address inside the hosts(/etc/hosts) file in your system

Go to your browser and type hosts that you provided in your ingress.yaml file

This is how you can use ingress
