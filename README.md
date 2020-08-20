# SelfieLess Acts

A social media application for users to share selfies of their selfless acts and allowing other users to like and comment on them. It was built on the MEAN stack and hosted on AWS. It follows a microservice architecture with two containerised micorservices: users and acts. AWS ELB is used for directing traffic to the respective EC2 instance for each microservice where a custom orchestrator written in Python using Flask provides auto scaling, high availibility and fault tolerance of services. The orchestrator track number of requests and spawns Node.js containers for every 200 requests in a minute. It also runs a heartbeat check on all Node.js and MongoDB containers every 2 seconds and respawns unresponsive containers. There are 3 MongoDB containers on each EC2 instance with a replication factor of 2. Thus, the entire application is scalable, fault tolerant and highly available.

![Orchestrator][/selfiless/orches.png]
