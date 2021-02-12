#Exercise 9.2
##Launch an Amazon eCS Cluster and Containers
1.	Launch the Amazon ECS console.
2.	Create a new cluster with an Amazon EC2 container instances.
3.	Create a new task definition that launches a WordPress and MySQL container.
4.	Use the official images from **Docker Hub**:
a.	*https://registry.hub.docker.com/wordpress/*
b.	*https://registry.hub.docker.com/mysql/*
5.	Create a new service that launches this task definition on the cluster.
6.	Copy the public IP address, and paste it into a web browser to access WordPress on the cluster instance.
7.	Modify the service to launch two tasks.
As the second task attempts to launch, note that this will fail because of the ports configured in the task definition already being registered with the running containers.
8.	Launch an additional cluster instance in your cluster.
9.	Monitor the service status to verify that the second task deploys to the new cluster instance.
