# kubernetes
# Web application on kubernets
In this application we have mongodb , mongo-express , secrets , services , configmaps
firstly we need to start the minikube 
# minikube start
 
then create secure credentials
# kubectl apply -f mongo-secret.yaml
to check the credentials
# kubectl get secrets
![img](https://github.com/user-attachments/assets/164d2cf3-991a-4060-a7fb-7a46b223f75a)
 
 
then deploy the mongo-db backend by 
# kubectl apply -f mongo-deployment.yaml
to view all the resources 
# kubectl get all
![img](https://github.com/user-attachments/assets/25607bc1-7ed2-4f1c-8676-0cd743efb6a9)
 
 
then create the configmap for the non senstivite data
# kubectl apply -f mongo-configmap.yaml
to view the configmaps 
# kubectl get configmaps
![img](https://github.com/user-attachments/assets/d8a378ba-0106-47d7-b0d5-3f108df6cd88)
 
 
then create the mongo-express for the frontend admin interface
# kubectl apply -f mongo-express.yaml
![img](https://github.com/user-attachments/assets/fc477f99-3c52-47e7-b89e-8466743e0004)
 
 
then brower will display the logging option to access the mongodb 
then enter the user name as my-admin-user
and password as my-super-password 
![img](screenshots/image4.png)
 
then we can access the mongodb interface and we can create a database and also we can delete 
![img](screenshots/image5.png)
 
 
to clean up all the resources 
kubectl delete -f mongo-express.yaml
kubectl delete -f mongo-deployment.yaml
kubectl delete -f mongo-configmap.yaml
kubectl delete -f mongo-secret.yaml