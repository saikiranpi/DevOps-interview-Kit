![Yellow Bold Minimal Book Reviews Youtube Thumbnail](https://github.com/saikiranpi/DevOps-interview-Kit/assets/109568252/8a9575b0-5c3f-4bca-b420-c1fcd152ac00)


# 45 minutes Before DevOps Interview

AWS Questions

Q - what is AMI? 

A - AMI is an Amazon machine image mainly contains operating system and configuration files which is mainly used to deploy multi virtual machines, regardless of any AWS region 

Q- what is EC2 instance , and what are the types?

A- EC2 is a virtual machine that represents your physical machine for you to deploy an application
General purpose, compute optimised, memory, optimised, accelerated, compute instance, storage optimisation, instance

Q-Different types of storage ? 

A elastic block storage, instant storage, both comes under block storage itself only

File storage : elastic file system and then AWS FSx
Elastic file system is mainly used for Linux operating system. Aws fSx is mainly useful Windows operating system. 

Object Storage -S3, glacier. 

Challenges with instant storage-it’s a temporary storage data will be lost if you stop and start the instance 
Fixed size and type 
Only available with the selected Instance  types 
Cannot detach and attach to other virtual machines 
Advantage of EBS-permanent or persistent storage
Can be increased to 16 TB 
available in different types, like SSD and HDD 
EBS is available to all servers 
Can be detached attached to others

Q-What are the different types of load balances?

A- Application load balancer works on HTTP and HTTPS protocol and network load balancer works on TCP and UDP protocol. Even application load balancer works on TCP protocol, but application load balancer doesn’t support UDP.
Because UDP is very efficient protocol when we are using streaming application or online meetings or any sort of streaming things, it is very useful. This is not supported by application load balancer. This is the major difference.

The major disadvantage with the network load balance is HTTP to https direction is not possible and also web application file was not supported.

Q- what are the different types of auto skilling groups we do have?

A- vertical scaling -increasing resource of existing servers, example T2 micro 2 T2 large needs to stop and start if we have multiple servers and we want to change the size of the instance it is not possible so we choose horizontal scaling example DB servers, file, servers, APP servers for this server, vertical scaling is best suited

Horizontal scaling-it will automatically create servers while the load is increasing

Q- what are the different types of route 53 routing policies we do have??

A - latency -latency means it will take the nearest data centre. To avoid the latency.

Failover -if one server goes down, the secondary server will take over

Weighted -example, there are a lot of uses in India due to large scale users. All the heads are going to US using latency to avoid such things we need to load balancing that is waited.

Geo location -Jio location will strictly follow the band rules, Indian New Zealand should go to India only and US region. User should go to US only.

Multivalues -we can give multiple server IP in multi values, specifically, it takes any one of the IP. 

Q- what is CDN ?

A- a large portion of all internet content is delivering through CNCN is nothing but content deliver network

Example, if you are in India and want to watch the same brand in USA store, we will experienced bit slow response to avoid such issues. CDN will store cache version of the US website content in multiple geographical locations across the world also called as point of presence. 

Q- How do you clear cash memory in cloud front  ?

A - go to cloud front under cloud front. We do have something called distributions under distributions. > invalidation  enter /* and then clear.

Q- what are the different types of databases we do have?

A - structure database-RDBMS MYSQL ,  Oracle MSSQLPostgress mariaDB Arora. 

Structure database, AWS dynamo DB AWS document DB

In memory database, elastic cache, AWS redshift 

Q- what is systems, Manager ?

A- Systems, Manager is mainly used to centrally, manage the global configuration settings by using parameter store. 

Q- what is the difference between AWS cloud Trail and AWS Config?

A - yes, we can monitor all the API activities activities such as logging in from console or CL or any third-party application like Packer and Terraform, everything all events will be recorded by the cloud Trail

Cloud config-Cloud conflict, especially used to tracking the detail changes which is happening on your resources. For example, if we make a 3,4 changes in your resources, you have a separate plural event, but in cloud conflict, it will show you consolidated overview. What are the changes it’s been performed.

Q- what is elastic beanstalk?

A - elastic beans, stock is the service for deploying and scaling web application and service. Upload your code and elastic bet will automatically handle the deployment from load balance into health monitoring.


Q- what is blue green  deployment?

A- we had an application which is currently running and that application had an new updates. So all the traffic will be hit to load balance, so we will direct the traffic to the already existing application. Once testing part is done. Then we will route the traffic to the newly deployed application.


DevOps Questions

Q what are the types of branching strategies you do follow?

A - we are following future branching strategies, which are main and integration which are long live branches
Main always points to the production comments, and the total code is available in the integration branch
So whenever we want to work on Application code, we create branch from the integration we developed, and we check if the pipeline is running smooth or amount. Once it is good, we will raise the PR.
If the PR conditions that the code is working, then only we merge.
So once marking with the integration, if it’s good, then we will check with the rest of the teams like QA pre-product production
So once it is succeeded in the production master points to the committee, so we point the tip and tag as version 1.0
By doing this, whatever the conflict, I will get, I will sit with the developers, and I will do the necessary things.

Q What is Git and why is it used? 

A - Git is a tool for tracking changes in code. It helps developers work together and keep track of every change.

Explain the difference between Git and GitHub. 
A-Git is the tool that tracks changes in code. GitHub is a website where you can store and share your code using Git.

What is a repository in Git? 

A-A repository is like a folder for your project. It contains all your project files and the history of changes made to those files.

Q-What does the git init command do? 

A-git init creates a new Git repository. It sets up all the necessary files for Git to start tracking changes.

Q-What is a commit in Git? 

A-A commit is a snapshot of your project. It records what the project looks like at a certain point in time.

Q-How do you check the status of your repository? 

A-Use the git status command. It shows you the changes that have been made and not yet committed.

Q-What does git add do? 

A-git add stages changes. It tells Git to include the changes in the next commit.

Q-What is the purpose of git clone? 

A-git clone copies a repository from a remote server to your local machine.

Q-What does git pull do? 

A-git pull updates your local repository with changes from a remote repository.

Q-What is a branch in Git? 

A-A branch is like a separate line of development. It lets you work on new features without changing the main codebase.

##################GIT########################
_____________________________________________________________________________________
##################Terraform########################

What is terraform and what are the advantages?

Terraformism is an infrastructure automation tool, which is mainly used to deploy/provision our cloud infrastructure. 
The main advantages inform is automation dry checks, validation of code, with the help of state file or TF. We can deploy another infra. 

Q - how to change a configuration file, which is already created using a terraform-

A- Terraform import

Q - What is the use case of Terraform statefile.tf And where you save it?

A- Terraform maintenance state file that map share current state of your infrastructure along with the configuration file 
So state files are basically in local machine for the back ups or in the remote location. S3 with strategies with the help of dynamo DB table locking policy. 

Q-let’s say you have lost your Terraform state file. What will you do?

A- basically, statefile will contain very critical information. So keeping such files under locking system is always the best practice. Imagine you have lost the file so performs don’t know that there is an existing environment because the state file has been deleted. So if we deploy again with the source file, there will be a drastic overlapping and we and we see  cross pollinations. so the best option is to use share of import.

Q- what are the main features in terraform?

A- terraform  can manage infrastructure in multiple cloud platforms. Terraform  uses HashiCorp language which is user readable.

Q What are the different types of terraform  modules? 

A- There are multiple modules, but I have knowledge on route  modules, publish modules . route modules which consists of all resources defined in the TF file which is the main working directory. Example it contains  main.Tf or variable.tf or any additional terraform  config  Files. 

The route modules  will be considered as main configuration for your entire infra project.

Q- have you know what is remote backend?

A- remote back in is a place where we store  all our TF state files which can be shared to other developers of infrastructure

Q- What are terraform  workspace?

A- it is allows  us to manage separate file for each workspace.


##################Terraform########################
_____________________________________________________________________________________________________________________

##################Jenkins########################

Q- how do you store Jenkins  secrets?

A- Jenkins credentials or any third-party tools, such as AWS, secrets, manager or Google cloud key management or Azure key or HashiCorp vault . 

Q- what are shared modules in Jenkins?

A- shared modules in Jenkins refers to collection of reusable and resource that can be shared across multiple Jenkins jobs. 

Q- can you use Jenkins to build application with multiple programming languages using different agents in different stages?

A- Yes, Jenkin can be used to build applications with multiple programming languages by using different bill agents in different stages of build 
process

Q- what is the difference between freestyle project and pipeline project?

A- Freestyle Project is traditional way of approach to Building and Testing, where we do things manually through the web interface

 pipeline project is the way of approach that uses cod usually in form  of Jenkins or integrating git to automate steps to software delivery process

Q- What are Jenkins plug-in?

A- Jenkins plug-in are additional software components, that extend the functionality of the software they are used to integrate with another software and to automate various tasks. Some examples GIT plug-in docker, pipeline plug-in, AWS plug-in, Sónar, Q plug-in, Maven plug-in. Etc 

Q- what is build node  ?

A- Jenkins build note is a machine that Jenkins uses to execute build job . It can be machine or virtual machine, or it can be run on premises or on cloud.

Q- What are the different types of Jenkins jobs?

A - freestyle 
pipeline 
Maven
multi branch pipeline '
GitHub organisation 
parameter job

Q- How can you test and destroy Jenkins pipeline?

A-we can use Jenkins bridal features to validate the syntax and structure of the Jenkins file
Breakdown the pipeline stages and check independently to isolate and identify problems 
Log reviews error to identify the warning in other issues 

Q-how can you manage build artefacts in Jenkins?

A- Jenkins provides several options for managing build  artefacts, including the use of the artefacts post build actions which allows you to archive files generated by the build . 
You can also use the copy artefact plug-in to copy, build artifacts  from one job  to another . 

##################Jenkins########################
_____________________________________________________________________________________________________________________

##################ANSIBLE########################

Q-What is Ansible and what is it used for?

A-Ansible is an open-source automation tool used for configuration management, application deployment, task automation, and orchestration. It simplifies IT operations by automating repetitive tasks.

Q-Explain the difference between Ansible and other configuration management tools like Chef or Puppet.

A-Ansible uses an agentless architecture, relying on SSH and Python to execute tasks on remote servers. Chef and Puppet use an agent-based approach where agents need to be installed on managed nodes.

Q-What are Ansible playbooks?

A-Ansible playbooks are YAML files that define a set of tasks to be executed. They automate configurations, deployments, and orchestration of tasks across managed nodes.

Q-How do you run an Ansible playbook?

A-You run an Ansible playbook using the ansible-playbook command followed by the playbook filename. For example, ansible-playbook site.yml.

Q-What is an Ansible role?

A-An Ansible role is a way to organize playbooks and other files in a reusable structure. It encapsulates tasks, variables, templates, and files into a directory structure.

Q-How do you install Ansible on your local machine?

A-Ansible can be installed using package managers like apt, yum, or brew depending on your operating system. For example, sudo apt-get install ansible on Ubuntu.

Q-What is an inventory file in Ansible?

A-An inventory file in Ansible lists the IP addresses or hostnames of managed nodes (servers) that Ansible will work with. It defines the targets for Ansible playbooks and ad-hoc commands.

Q-Explain the difference between Ansible ad-hoc commands and playbooks.

A-Ad-hoc commands are run from the command-line to perform quick tasks on remote nodes (ansible command). Playbooks are YAML files that provide a more structured and reusable way to automate tasks.

Q-How does Ansible handle idempotency?

A-Ansible ensures idempotency by only applying changes when necessary. If a task has already been completed successfully, Ansible will not reapply it unless changes are made to the task or its configuration.

Q-What is the Ansible Galaxy?

A-Ansible Galaxy is a website and command-line tool for finding, reusing, and sharing Ansible roles. It provides a repository of community-contributed roles that can be used to extend Ansible functionality.

##################ANSIBLE########################
_____________________________________________________________________________________________________________________

##################Docker########################

What is Docker and why is it used?

A-Docker is a platform that allows you to package, distribute, and run applications in containers. It's used for creating consistent environments across development, testing, and production.

What is a container?

A-A container is a lightweight, standalone, and executable package that includes everything needed to run a piece of software, including code, runtime, libraries, and dependencies.

Explain the difference between a Docker image and a Docker container.

A-A Docker image is a read-only template that contains the application and its dependencies. A Docker container is a runnable instance of a Docker image.

How do you create a Docker container?

A-You create a Docker container by running an image with the docker run command. For example, docker run -d -p 8080-80 nginx runs a container based on the nginx image in detached mode, mapping port 8080 on the host to port 80 in the container.

What is Docker Hub?

A-Docker Hub is a cloud-based registry service that allows you to store and share Docker images publicly or privately. It's a repository of Docker images maintained by Docker.

How do you list running Docker containers?

A-Use the docker ps command to list all running containers. Adding the -a flag (docker ps -a) lists all containers, including stopped ones.

What is the purpose of a Dockerfile?

A-A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image. It's used to build Docker images automatically.

How do you stop and remove a Docker container?

A-Use the docker stop command followed by the container ID or name to stop a running container. Then, use docker rm followed by the container ID or name to remove a stopped container.

Explain the concept of Docker volumes.

A-Docker volumes provide a way to persist data generated by and used by Docker containers. They are stored outside the Union File System and can be shared among containers.

What are Docker networks and why are they used?

A-Docker networks allow containers to communicate with each other and with other non-containerized devices on the same network. They are used to facilitate communication and isolation between containers.

##################Docker########################


Kubernetes Questions

What is Kubernetes and why is it used?

A-Kubernetes is an open-source platform for automating the deployment, scaling, and management of containerized applications. It helps in managing containerized applications across multiple hosts.

What is a container?

A-A container is a lightweight, executable package of software that includes everything needed to run a piece of software, including code, runtime, libraries, and dependencies.

Explain the difference between Kubernetes and Docker.

A-Docker is a platform for building and running containers, while Kubernetes is a container orchestration platform that manages the deployment and scaling of containers.

What are Pods in Kubernetes?

A-Pods are the smallest and simplest Kubernetes objects. They represent a single instance of a running process in the cluster, which may consist of one or more containers that share storage and network resources.

How do you create a Pod in Kubernetes?

A-You create a Pod by defining a Pod manifest file in YAML format, which specifies the Pod's configuration, such as containers, volumes, and metadata. Then, you apply this manifest file using kubectl apply -f pod.yaml.

What is a Deployment in Kubernetes?

A-A Deployment in Kubernetes manages a set of identical Pods, ensuring that the desired number of Pods is running and handling updates and rollbacks.

How do you create a Deployment in Kubernetes?

A-You create a Deployment by defining a Deployment manifest file in YAML format, which specifies the desired state of the Deployment, including the number of replicas and the Pod template. You then apply this manifest file using kubectl apply -f deployment.yaml.

What is a Service in Kubernetes?

A-A Service in Kubernetes is an abstraction that defines a logical set of Pods and a policy by which to access them. It provides a stable endpoint for connecting to the Pods.

How do you expose a Deployment as a Service in Kubernetes?

A-You expose a Deployment by creating a Service manifest file in YAML format, which specifies the type of Service (e.g., ClusterIP, NodePort, LoadBalancer) and selects the Pods to expose. You apply this manifest file using kubectl apply -f service.yaml.

What is the role of kubectl in Kubernetes?

A-kubectl is the command-line tool used to interact with Kubernetes clusters. It allows you to deploy and manage applications, inspect and manage cluster resources, and view logs and troubleshooting information.

What is a Namespace in Kubernetes?

A-A Namespace in Kubernetes provides a way to divide cluster resources among multiple users or projects. It helps organize and isolate resources within a cluster.

How do you scale a Deployment in Kubernetes?

A-You scale a Deployment by updating the replicas field in the Deployment manifest file to the desired number of replicas (e.g., kubectl scale deployment/myapp-deployment --replicas=3).

What is a ConfigMap in Kubernetes?

A- A ConfigMap in Kubernetes is an API object used to store non-sensitive configuration data in key-value pairs. It can be used to decouple configuration from Pods and containers.

How do you manage application logs in Kubernetes?

A-Application logs in Kubernetes can be accessed using kubectl logs command followed by the Pod name and optional container name. For example, kubectl logs mypod.

What is a Node in Kubernetes?

A-A Node in Kubernetes is a worker machine in the cluster. It may be a physical machine or a virtual machine, and it runs Pods managed by the Kubernetes control plane.

What are Labels and Selectors in Kubernetes?

A-Labels are key-value pairs attached to Kubernetes objects (e.g., Pods, Services) for identification and grouping. Selectors are used to filter and select objects based on labels.

How does Kubernetes handle container restarts?

A-Kubernetes automatically restarts containers that fail or exit, based on the Pod's restartPolicy (default is Always). It ensures that the desired state of the Pod (defined in the Deployment or Pod manifest) is maintained

What is a Persistent Volume (PV) in Kubernetes?

A- A Persistent Volume in Kubernetes is a piece of storage in the cluster that has been provisioned by an administrator or dynamically provisioned using StorageClasses. It provides storage resources for Pods.

How do you upgrade Kubernetes cluster components?

A- Kubernetes cluster components (e.g., API server, Controller Manager, Scheduler) can be upgraded by updating the Kubernetes version in a controlled manner, following the upgrade instructions provided by the Kubernetes documentation.

What is the difference between a StatefulSet and a Deployment in Kubernetes?

A- A StatefulSet is used for stateful applications that require stable, unique network identifiers and persistent storage. It manages Pods that are not interchangeable, whereas a Deployment is used for stateless applications and manages interchangeable Pods.

