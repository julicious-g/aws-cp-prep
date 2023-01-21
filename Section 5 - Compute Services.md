#aws #cloud-computing 


# Computing 101

computer consist of 
- CPU. 
- RAM. Non persistent.
- Storage (HDD or SSD. Persistent
- Network interface card(NIC)

measurements
- CPU - Ghz
- RAM - GB
- HDD or Storate - GB
- NIC - Mbps or Gbps


# Amazon Elastic Compute Cloud (EC2)

EC2 host is the server computer where EC2 instances are running.

EC2 instance is a virtual server

EC2 instances has type. Which vary in the combination of CPU, memory, storage and network

## Instance types

Instance type is a hardware profile. some of the profiles are

| Family            | Type       | vCPUs | Memory(Gib) |
|-------------------|------------|-------|-------------|
| General Purpose   | t2.micro   | 1     | 1           |
| Compute optimized | c5n.large  | 2     | 5.25        |
| Memory optimized  | r5ad.large | 2     | 16          |
| Storage optimized | d2.xlarge  | 4     | 30.5        |
| GPU instances     | g2.2xlarge | 8     | 15          |

## AMI

Amazon Machine Image

consist of EBS snapshot, permissions and configuration

AMI define the configuration of the instance such as operating system

from AMI we can create EBS snapshot

we can customize our instances and create a custom ami

## Benefits of Amazon EC2

| Benefits          | Description                                                                |
|-------------------|----------------------------------------------------------------------------|
| Elastic computing | launch thousands of instances within minutes                               |
| Complete control  | control instances with root/administravite access                          |
| Flexible          | choice of instance types, OS and softwares                                 |
| Reliable          | high level availability. instance can be rapidly commissioned and replaced |
| Secure            | fully integrated with Amazon VPC and security features                     |
| Inexpesinve       | low cost and pay what you use                                              |


# User data and metadata

both are not encrypted

## User data

The ability to run commands when the service is starting

limited to 16KB

## Metadata

data about the instance. you can use to configure or manage the running instance

instance metada is available in http://ip-address/latest/meta-data


# Accessing services - Access keys and IAM Roles

there are to ways an EC2 instance to access other AWS service such as S3 or RDBMS. First is by using access keys. Access keys is stored inside the EC2 instance and therefore not secure. the second is by assuming a profile. Using a profile allows EC2 instance to connect to a specific IAM Role. by assuming an IAM role EC2 instance will gain permissions to access whatever services the role allowed or provide.

# AWS Batch

AWS Batch is a service that allows you to run a batch job.

a job is a unit of work such as shell script, executable or docker container image.

you have to define a job definition

job will put into job queue.

Batch launches, manages and terminates resources as required (EC2 and ECS/Fargate)


# Amazon LightSail

Similar with EC2 but less powerful and more simple.

AWS called it Amazon's Simple Cloud Server

Cheap, less feature rich

for somone with less technical expertise

Compute, storage and network

preconfigured virtual servers

virtual servers, databases and load balancesr

SSH and RDP access

can access Amazon VPC

Exam Tip: usually comes up in a use case where an easy method of deploying a virtual server is required by a user with little to no AWS expertise

simple management interface


## Amazon Elastic Container Service (ECS)

ECs is used to run Docker containers in the cloud
ECS containers are knows as tasks

Lauch types

1. EC2 - host for the running tasks
2. Fargate - AWS managed the compute, cluster and scaling

Amazon Elastic Container Registry : private container image registry






