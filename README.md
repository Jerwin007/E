deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: myapp
spec:
  replicas: 1
  selector:
    matchLabels:
      app: myapp
  template:
    metadata:
      labels:
        app: myapp
    spec:
      containers:
      - name: c
        image: nginx

command : 

kubectl apply -f deployment.yaml

kubectl get deployments
kubectl get pods

kubectl scale deployment myapp --replicas=2

kubectl expose deployment myapp --port=80 --type=NodePort
kubectl get svc
