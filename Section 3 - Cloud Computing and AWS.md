#aws #cloud-computing

# Traditional IT and Cloud Computing

TODO : add this

# Cloud Computing Models

- Infrastructure as a service
- Platform as a service
- Software as a service

# Cloud Deployment Types

- Public cloud or simply "cloud" -- AWS, Azure, GCP
- Hybrid Cloud -- mixture of public and private cloud
- Private cloud (on premise) -- manage your own server (data center)
- Multicloud -- combination of public and private

# Pricing 

- Compute - CPU/RAM and duration
- Storage - quantity data stored and allocated
- Data transfer - inbound/outbound. data leaving AWS Region

# AWS Global Infrastructure

## AWS Regions

- Geographical area
- Consist of 2 or more **Availability Zones**
- Isolated from other AWS Regions

## Availability Zones

- physically separated and isolated from each other
- span one or more data centers
- each AZ is designed as an independent failure zone. In the event of failure or power outage in one AZ any services and resources can be made available in the other AX

## Local Zones

- place services and resources closer to end-users
- extensions of AWS Region to run latency sensitive applications

## Edge Locations and Regional Edge Caches

- edge locations are CDN endpoints for **CloudFront**
- there are many more edge locations than regions
- regional edge caches sit between CloudFront Origin servers and the Edge locations
- a regional edge cache has a larger cache-width than each of the individual edge locations


# AWS Shared Responsibility Model

## AWS is responsible for "security **of** the cloud"

- protecting the infrastructure that runs all the services offered in the AWS cloud
- this infrastructure composed of : hardware, software, networking and facilites than run AWS cloud services


## Customers are responsible for "security in the cloud"

- network level security
- operating system patches and update
- IAM user access management
- client and server side encryption
 
# 6 Advantages of Cloud Computing

1.  Trade capital expense to variable expense. Means that instead of having paid in front in a big amount you use pay as you go model where you pay what you use and when you use it. 
2. Massive economies of scale
3. Stop guessing capacity. You can use any services first and adjust it based on what you really need.
4. Increase speed and agility. 

Speed = deploy resources easily and quickly
Agility = react to chages; speed to market

5. stop spending money on maintaining data centers

6. Go global in minutes



