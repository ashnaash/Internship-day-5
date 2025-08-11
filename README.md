# Build a Kubernetes Cluster Locally with Minikube

## Objective
Deploy and manage applications in Kubernetes using Minikube, kubectl, and Docker.

## Tools Required
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [Docker](https://www.docker.com/)

## Deliverables
- YAML files (deployment.yaml, service.yaml)
- Screenshots of pods and services

## Steps

1. **Install Minikube & Start the Cluster**
   ```bash
   minikube start
Create a Deployment

Create a deployment.yaml file for your app.

yaml
Copy
Edit
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
spec:
  replicas: 2
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-app-container
        image: nginx
        ports:
        - containerPort: 80
Apply the deployment:

bash
Copy
Edit
kubectl apply -f deployment.yaml
Expose the Application

Create a service.yaml file.

yaml
Copy
Edit
apiVersion: v1
kind: Service
metadata:
  name: my-app-service
spec:
  selector:
    app: my-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
  type: NodePort
Apply the service:

bash
Copy
Edit
kubectl apply -f service.yaml
Verify Pods

bash
Copy
Edit
kubectl get pods
Scale Deployments

bash
Copy
Edit
kubectl scale deployment my-app --replicas=3
Describe Resources & Check Logs

bash
Copy
Edit
kubectl describe pod <pod-name>
kubectl logs <pod-name>
Outcome
By completing this task, you’ll understand:

How to deploy apps in Kubernetes

How to manage deployments and services

Basic pod scaling and log inspection

yaml
Copy
Edit

---






