# Setting up Elasticsearch and Kibana locally using Kubernetes

This deployment script is to deploy Elasticsearch and Kibana locally using Kubernetes. It allows browser access without setting up Ingress.

1 Pod, 1 Node. You can scale as according.

Using minikube and kubectl

Once Elasticsearch and Kibana are deployed, run the following command to get the URL:
```
minikube service <service name> --url
```

Copy and paste the URL on your browser to access. You will need the username (elastic) and password to login.

To get the password:
```
kubectl get secret
kubectl get secret <name for your Elasticsearch cluster elastic user> -o go-template='{{.data.elastic | base64decode}}'
```
