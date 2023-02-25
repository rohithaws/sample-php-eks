# sample-php-eks
We will build a Docker image for users and shifts by entering into respective folders using below command
* docker build -t <app name> .
* After builing the image we will push the Docker image to ECR repository 
* Then we will update the image details in the deployment.yaml
* Then we will go to respective app folder and apply all kubernetes yaml files
* kubectl apply -f <app folder>/
* Then you can access the app using the respected app LoadBalancer URL   
  
3.) Ensure the deployment can handle rolling deployments and rollbacks.

Answer: Rolling deployments and rollbacks are important aspects of software deployment that ensure that new updates or changes are smoothly rolled out to a system, and any issues or bugs that are discovered can be quickly addressed by rolling back to the previous stable version. Here are some steps to ensure that your deployment can handle rolling deployments and rollbacks:

Use version control: Version control is essential for managing code changes and tracking the progress of deployments. Use a version control system like Git to keep track of all changes to the codebase.
  
Automate deployment: Use automation tools like Jenkins, Travis CI, or CircleCI to automate the deployment process. This will help reduce the risk of human error and ensure that the deployment is consistent and reliable. 

4.) Your development team should not be able to run certain commands on your k8s cluster, but you want them to be able to deploy and roll back. What types of IAM controls do you put in place?

Answer: By using RBAC – Role based Access control, Kubernetes RBAC provides authorization for access to cluster resources based on user roles and permissions. You can create a separate role with limited privileges that only allows the team to deploy and roll back, and deny access to certain commands.
 
Attribute-based Access Control (ABAC): ABAC is another Kubernetes access control mechanism that allows you to define policies based on attributes. You can create policies that only allow deployment and rollback based on specific attributes like labels, annotations, or namespaces. Also, we have other options like Kubernetes namespaces, Kubernetes admission controllers, Kubernetes secrets.

# Bonus:

. How would you apply the configs to multiple environments (staging vs production)?

Answer: To apply configurations to multiple environments, there are several approaches you can take, depending on the nature of your configurations and the number and complexity of your environments.

Identify the environments: First, identify the environments where you need to apply the configurations. These could be different stages of your development, testing, staging, and production environments, or different regions or branches of your codebase.
Create a configuration template: Create a template for your configurations that includes all the parameters that need to be configured, but without the specific values for each environment. This could be a JSON or YAML file, or a set of environment variables.
Test the configurations: Once the configurations have been applied to each environment, test the applications or services to ensure that they are functioning correctly.
Monitor the configurations: Monitor the configurations in each environment to ensure that they remain up-to-date and continue to meet the needs of the application or service.

· How would you auto-scale the deployment based on network latency instead of CPU?

Answer: Auto-scaling based on network latency can be useful in scenarios where the performance of a service or application is highly dependent on network connectivity, and CPU utilization may not be the best indicator of the application's ability to handle user requests.

Monitor network latency: The first step is to collect data on network latency. This can be done by monitoring the round-trip time (RTT) of requests between the application and its clients or between different components of the application. The data can be collected using a monitoring tool or by building custom instrumentation into the application.
  
Define scaling policies: Once the latency data is collected, it can be used to define scaling policies. For example, a policy could be defined to scale up the application when the average latency exceeds a certain threshold or to scale down when the latency drops below a certain level.
  
