#aws #cloud-computing 

# Storage systems (Block vs File vs Object )

## Object Storage

Uses a REST API to manage object
No hierarchy of object in the container
Massively scalable and low cost


## AWS Storage Services

| Storage Type   | AWS Service                       |
|----------------|-----------------------------------|
| Block          | Amazon Elastic Block Store        |
| File Storage   | Amazon Elastic File System        |
| Object Storage | Amazon Simple Storage Service(S3) |


# Amazon Elastic Block Store(EBS)

each instance created automatically as EBS atached to it
each ec2 instance can have an EBS Volume attached to it or more
we cant attach multiple ec2 instances to a single volume
EBS volume lives within AZ. You cant attach ec2 instance in another AZ

exam tips : gp2 type is general purpose while io1 is proivsioned input output. gp2 attached to instance by default.

EBS volume data persists independently of the life of instance
EBS volume do not need to be attached to an instance
Many EBS volume can be attached to a single instance

Root EBS volume is deleted on termination by default(you can turn that off)

# Amazon EBS Snapshots and DLM

Snapshot is point-in-time state of an instance. stored in S3. not attached to AZ but region. Snapshots are incremental. you can use snapshot to create EBS in another AZ. we create AMI from snapshot.


## Amazon Data Lifecycle Manager (DLM)

DLM automates the creation, retention and deletion of EBS snapshots and EBS backed AMIs

DLM helps with:
- protect valuable data by enforcing a  valuable backup
- create standardize AMIs that can be refresh at regular interface
- Retain backups required by auditors or internal compliance
- deleting outdated backup to reduce storage cost
- create disaster recovery


## EBS vs Instance Store

EBS volumes are attached overa the network.

Instance stores volumes are physically attached to the host.
Attached locally to EC2 instance.
Instances Stores are ephemeral. data is lost when instance is powered down. use for temporary data.
Instance stores are faster than EBS



# Amazon Elastic File System (EFS)

can simultaneously connect thousands of instances
can connect from other VPCs
only available for linux instances
use NFS protocol
on-premise computer can be connected through VPN or Direct Connect

# Amazon Simple Storage Service (S3)


we create a container where our object are stored called bucket.
object consist of
- key (name of objects)
- version id
- value (actual data)
- metadata
- subresources
- access control information

for instances that are inside a vpc, they can connect to S3 services through public addreses or privately using S3 gateway endpoint.

you can store any type of file
0 byte to 5TB
unlimited storage available
S3 is a universal namespace. bucket must be unique globally
you create bucket within a region
best practice to create buckets in regions that are closerst to users to reduce latency


## additional features

| S3 Capability              | What it does                                                                           |
|----------------------------|----------------------------------------------------------------------------------------|
| Transfer Acceleration      | Speed up data uploads using CloudFront in reverse                                      |
| Requester Pays             | The requester rather than the bucket owner pays for requests and data transfer         |
| Events                     | Trigger notifications to SNS, SQS or Lambda when certain events happend in your bucket |
| Static web hosting         | simple and massively scalable static website hosting                                   |
| versioning and replication | retain versions of objects and replicate objects within and accross AWS regions        |


# Amazon S3 Storage Classes

## Availability and Durablity

Availability
- how readilty available the service is
- measured as a percentage
- varies between storage classes

Durability
- likelihod of data list
- all storage classes offer 9/11 % durability

## Classes

- Standard
	- no retrieval fee
- Intelligent Tiering
	- no retrieval fee
- Standard-IA (infrequent access)
- One Zone-IA
	- persist in one zone only
	- availablity only 99.5%
- S3 Glacier
	- first byte latency in minutes or hours
- S3 Glacier Deep Archive
	- first byte latency definetly in hours


# S3 Versioning, Replication and Lifesycle Rules

Versioning means of keeping multiple variants of an object in the same bucket. To preserver, retrieve and restore

Replication means to copy object from a bucket to another bucket. There are two types
- cross-region replication (CRR)
- same region replication

bucket could also from the different account. bucket must have versioning enabled


# S3 Glacier

low cost and pay only what you need

two classes
- glacier
- deep archive

three options for access to archives

| type         | Expedited   | Standard  | Bulk       |
|--------------|-------------|-----------|------------|
| Glacier      | 1-5 minutes | 3-5 hours | 5-12 hours |
| Deep archive | N/A         | 12 hours  | 48 hours   |

## Object lock and Glacier vault lock

S3 object lock

store object using write once read many
prevent object from being deleted or overwritten for fixerd time or indefinetly

S3 Glacier vault lock

also enforce worm
can apply policy and lock policy from future edit
use for compliance objectives and data retention

# AWS Storage Gateway

connect on-premise application onto cloud storage services
use cases
- moving backups to the cloud
- low latency access to data in aws 
- disaster recovery




