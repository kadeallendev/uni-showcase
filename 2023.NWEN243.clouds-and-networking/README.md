# NWEN243 Clouds and Networking

This course provides a broad introduction to computer networks and a basic understanding of network application programming, with an emphasis on the working principles and application of computer networks. It covers a range of introductory topics including the essentials of data communication, computer network concepts, protocols, network applications and cloud computing. Some of these topics are: cloud infrastructure (VMs), containers and micro-services, and layered network stack model.

## Course Learning Objectives

1. Explain the basics of networks and the design of their associated protocols.
2. Explain how networks are utilised for various roles.
3. Explain the role of the application layer, the socket API and the basics of building networked, cloud, or distributed applications and the design of their associated protocols.
4. Implement applications that make use of the Socket API and Cloud computing, including at least two cloud service level paradigms.

## Assignments

There were three assignments.

### Assignment 1

This assignment involved:
- Investigating IP address information
- Packets
- Investigating a TCP handshake
- Creating a simple Java web server using TCP sockets to render a web page with the client's IP address

### Assignment 2

This assignment involved creating two Java applications, a server and a client, which would communicate over TCP. The client system would send a request to the server with a specified year. The server, upon a request, would read a JSON file containing the top ten songs of each year and select a random song from the specified year and reply with that song's information. The server system was then deployed onto an EC2 instance on AWS. An AMI template was created from the original EC2 instance, and used to replicate the original instance.

### Assignment 3

This assignment built off of the last assignment, consisting of two parts.

In the first part, we created a VPC (virtual private cloud) with two subnets. An internet gateway was then attached to this VPC. A security group was created an attached to control access to the VPC. We created a launch template to easily create new instances of the same service. We used a load balancer and auto scaling group to control and manage the instances. I tested the load balancer and auto scaler by sending a large amount of requests to the service, evaluating the instances' status and performance.

In the second part we used Docker to containerize the server application, pushing the image to the docker registry. Multiple replicas of this image were deployed using AWS Fargate.
