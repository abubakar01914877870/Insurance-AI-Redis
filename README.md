Redis repo

Running Redis Locally with Docker:
Install Docker: If you haven't already, install Docker on your local machine. You can find installation instructions for various operating systems on the Docker website.

Run Redis Container: Open a terminal and run the following command to pull the Redis image from Docker Hub and run it as a container:

bash
Copy code

docker run --name insurance-ai-redis -p 6379:6379 -d redis

This command will start a Redis container named my-redis-container in detached mode.

Verify Redis Container: To verify that the Redis container is running, you can use the following command:

bash
Copy code

docker ps

This command will list all running containers, and you should see your Redis container in the output.

Running Redis Locally with Docker:
Install Docker: If you haven't already, install Docker on your local machine. You can find installation instructions for various operating systems on the Docker website.

Run Redis Container: Open a terminal and run the following command to pull the Redis image from Docker Hub and run it as a container:

bash
Copy code
docker run --name my-redis-container -d redis
This command will start a Redis container named my-redis-container in detached mode.

Verify Redis Container: To verify that the Redis container is running, you can use the following command:

bash
Copy code
docker ps
This command will list all running containers, and you should see your Redis container in the output.

Deploying Redis to Google Cloud:
Set Up Google Cloud SDK: If you haven't already, install the Google Cloud SDK on your local machine. Follow the instructions provided in the Google Cloud documentation.

Create a Google Cloud Project: Using the Google Cloud Console, create a new project or select an existing one where you want to deploy Redis.

Enable Google Kubernetes Engine (GKE): In the Google Cloud Console, navigate to the Kubernetes Engine section and enable the Kubernetes Engine API.

Create a Kubernetes Cluster: Use the following command to create a Kubernetes cluster using Google Kubernetes Engine (GKE):

bash
Copy code

gcloud container clusters create insurance-ai-redis --num-nodes=1 --zone=us-central1 --disk-size=10

Replace my-cluster with your desired cluster name and your-preferred-zone with your preferred GCP zone.

Deploy Redis to Kubernetes: Create a Kubernetes deployment YAML file for Redis. Here's a simple example:

kubectl apply -f redis-deployment.yaml

kubectl expose deployment insurance-ai-redis --port=6379 --target-port=6379 --type=ClusterIP
