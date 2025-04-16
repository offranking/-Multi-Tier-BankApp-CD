# -Multi-Tier-BankApp-CD

## MySQL Deployment in Kubernetes

This project includes a Kubernetes configuration for deploying a MySQL database, used by the Bank App for data storage and retrieval.

###  What's Included

1. **Deployment** (`mysql`):
   - Uses the official MySQL 8 Docker image.
   - Sets environment variables for:
     - `MYSQL_ROOT_PASSWORD` – the root password of MySQL.
     - `MYSQL_DATABASE` – the default database created on startup (`bankappdb`).
   - Exposes container port `3306` for internal communication.

2. **Service** (`mysql-service`):
   - A Kubernetes service that exposes the MySQL pod on port `3306`.
   - This allows other services in the cluster (like your app backend) to connect to MySQL using the service name `mysql-service`.

###  How to Deploy

1. Make sure your Kubernetes cluster is running (e.g., using Minikube, Docker Desktop, or a cloud provider like GKE/EKS).
2. Apply the MySQL deployment and service using:

   ```bash
   kubectl apply -f mysql-deployment.yaml

3. Verify that the pod and service are up and running:

```
kubectl get pods
kubectl get svc
```
### Credentials


| Root Password	|Test@123
| Database Name |	bankappdb |
| Service Name	| mysql-service |
| Port	| 3306 |
 For production deployments, it's strongly recommended to store credentials securely using Kubernetes Secrets.
