# Assignment 02
## Problem Statements
In this assignment you have to learn about deployment strategies: - Recreate deployment - Rolling deployment - Blue-green deployment - A/B deployment - Canary deployment

After this you need to implement these 2 below deployment strategies: Must Do - Recreate deployment - Rolling deployment Good to Do - Blue Green deployment - Canary deployment

Recommendation - Don't straight forward jump into creating the utility, first do it manually

github-link --> https://github.com/OT-TRAINING/DeploymentStrategies

Hint :

1.Use ASG
2.Use LB
3.Use EC2 service
4.Use AMI Snapshot
# Recreate Deployment
## Basic Requirements
Create VPC, 2 Subnets (Public and Private), Route Table, IGW Gateway, NAT Gateway
Create a instance for v1 and make the AMI of it.


![image](https://github.com/user-attachments/assets/8ee10969-2189-453c-8ea8-34b2a7b54090)

## Create a Target group for Load Balancer
![image](https://github.com/user-attachments/assets/d7e4349f-4c6e-4c77-9a20-239e75febe90)

## Create a Load Balancer and attach Target Group to it.
![image](https://github.com/user-attachments/assets/8e7b1fc4-2ab9-4edb-95f3-bbebf7344803)

## Create a Launch Template Create a Autoscaling group and attach Load Balancer to it.
![image](https://github.com/user-attachments/assets/aface549-61b5-4493-9cab-34d0d00e6eb1)

## Go to web browser and hit the Load Balancer dns
![image](https://github.com/user-attachments/assets/6b284f46-d489-4668-a61c-e5784d65a32b)

## Now change the version in Launch template and Go to the auto scaling group and change the capacity to zero.
## It will shows downtime and then increase the capacity. When the instance gets up it will shows V2.

![image](https://github.com/user-attachments/assets/273591aa-987c-4335-81db-c07b6d394aae)
![image](https://github.com/user-attachments/assets/182aac5b-7762-47fe-9218-6a222384972a)
![image](https://github.com/user-attachments/assets/ff64d8c9-188e-44b1-8e00-5ec9e8ad507e)

## Rolling Deployment
## Here we use same infrastructure as ablove in it.
## I have 3 servers running in v1 as shown below. By changing the capacity in Autoscaling group.
![image](https://github.com/user-attachments/assets/492e4c35-3f27-4799-bd77-8d3057017605)
![image](https://github.com/user-attachments/assets/b1463af9-fbed-49fe-8682-ce6dd354e98a)

## It will gradually increase the instances then we change the capacity in autoscaling group to desired as shown in below screenshots.
![image](https://github.com/user-attachments/assets/ad225fd6-20fa-4d0e-918e-bd14c7bbb407)

![image](https://github.com/user-attachments/assets/cac9c192-ed83-44f8-b5df-77a46c58a8b4)

## So due to this v1 replaces the v2 gradually with no downtime.
![image](https://github.com/user-attachments/assets/18c655a5-d419-4b12-8ef3-3c4ec6644ee9)
![image](https://github.com/user-attachments/assets/d5eccbf9-1b1a-4e3c-9c43-715e052ca61f)










