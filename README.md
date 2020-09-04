# automation_using_terraform_task6
Deploy the WordPress application on Kubernetes and RDS for Storage | AWS | Terraform

Use_Case:-
Write an Infrastructure as code using terraform, which automatically deploy the Wordpress application.

On AWS, use RDS service for the relational database for Wordpress application.

Deploy the Wordpress as a container either on top of Minikube or EKS or Fargate service on AWS

The Wordpress application should be accessible from the public world if deployed on AWS or through workstation if deployed on Minikube.

Task Description:
I have written Infrastructure as code using terraform, which automatically deploy the Wordpress application. On AWS, I have used RDS service for the relational database for Wordpress application. Then I deployed the Wordpress as a container on top of Minikube, the Wordpress application is accessible to the public world.

Pre-requisite:
AWS account

Minikube (Kubernetes) installed: https://kubernetes.io/docs/tasks/tools/install-minikube/

Terraform installed: https://learn.hashicorp.com/tutorials/terraform/install-cli

Kubernetes
Kubernetes is a portable, extensible, open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. Kubernetes is an open-source container-orchestration system for automating computer application deployment, scaling, and management. It was originally designed by Google and is now maintained by the Cloud Native Computing Foundation.

A Kubernetes cluster is a set of node machines for running containerized applications. If you’re running Kubernetes, you’re running a cluster. At a minimum, a cluster contains a control plane and one or more compute machines, or nodes. The control plane is responsible for maintaining the desired state of the cluster, such as which applications are running and which container images they use. Nodes actually run the applications and workloads.

For this task, I'll use Minikube, a tool that runs a single-node Kubernetes cluster in a virtual machine on your personal computer.

AWS RDS Amazon Relational Database Service (Amazon RDS)
Amazon Relational Database Service (Amazon RDS) makes it easy to set up, operate, and scale a relational database in the cloud. It provides cost-efficient and resizable capacity while automating time-consuming administration tasks such as hardware provisioning, database setup, patching and backups. It frees you to focus on your applications so you can give them the fast performance, high availability, security, and compatibility they need. Amazon RDS is available on several database instance types - optimized for memory, performance, or I/O - and provides you with six familiar database engines to choose from, including Amazon Aurora, MySQL, Oracle Database, etc. web service that makes it easier to set up, operate, and scale a relational database in the AWS Cloud. It provides cost-efficient, resizable capacity for an industry-standard relational database and manages common database administration tasks.

We'll configure our Wordpress app deployed on our Minikube cluster to use RDS as its Database.

Minikube is an open-source tool that helps to run Kubernetes on a local computer. Before using minikube we need to start it so here I wrote terraform code to start minikube on my Local Computer.

Let’s start
It will launch the Wordpress Application.
Wordpress.tf file:-
![t1](https://user-images.githubusercontent.com/54200130/92209893-67696480-eeab-11ea-9b04-b3dc0be7c3f7.jpeg)
![t2](https://user-images.githubusercontent.com/54200130/92210263-068e5c00-eeac-11ea-999c-0fc26c3ac59a.jpeg)

2. It will create the RDS on top of AWS.
databasesql.tf file:-
![t3](https://user-images.githubusercontent.com/54200130/92210417-4ce3bb00-eeac-11ea-8bc6-67b021955575.jpeg)

3. It will provide the IP to connect to Wordpress.
main.tf files:-
![t4](https://user-images.githubusercontent.com/54200130/92210589-a2b86300-eeac-11ea-9931-e4f0748a676e.jpeg)

After writing the terraform code. We have to run the command:

  terraform init
  
  terraform apply --auto-approve
  
  ![WhatsApp Image 2020-09-02 at 12 14 27 AM](https://user-images.githubusercontent.com/54200130/92210736-ea3eef00-eeac-11ea-9f03-bbf0e06a0b97.jpeg)

If you get everything green then you are on the right track and everything works fine. Also, we have deployed WordPress as a container on the top of Minikube.

![WhatsApp Image 2020-09-02 at 12 14 27 AM (1)](https://user-images.githubusercontent.com/54200130/92210969-515ca380-eead-11ea-8499-0c94507099a1.jpeg)

Now to get the IP for WordPress. In the command line type:

  minikube ip
  
  minikube service list
  
  kubectl get all
  ![t7](https://user-images.githubusercontent.com/54200130/92211423-13ac4a80-eeae-11ea-9244-e565ef03ad0f.jpeg)

Now Open minikube-nodes-ip:40000 and proceed with installation wizard:

![t8](https://user-images.githubusercontent.com/54200130/92211532-3a6a8100-eeae-11ea-9542-53cee44e89ba.jpeg)


![t9](https://user-images.githubusercontent.com/54200130/92211585-50784180-eeae-11ea-9a39-88f66e6ac659.jpeg)


![WhatsApp Image 2020-09-02 at 12 14 29 AM (1)](https://user-images.githubusercontent.com/54200130/92211691-77367800-eeae-11ea-95f4-acfd41741a7b.jpeg)


Thanka Alot for Giving Your Time..
