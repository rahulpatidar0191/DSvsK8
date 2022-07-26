## Docker swarm VS Kubernetes 
#### A brief intro of orchestration  
Orchestration is the automation of numerous tasks that run at the same time in a way that minimizes production issues and time to market.
**example of music conductor**

![dasd](https://user-images.githubusercontent.com/42219389/180896120-f31b716b-97c4-4b2f-8000-f068969c9bef.PNG)

#### 1. Installation and setup:
**Swarm**: There is simple installation with Docker, and instances are typically consistent across operating systems.

**Kubernetes**: Manual installation can differ for each operating system. No installation is required for managed offerings from cloud providers.
- Setting up you own cluster is complex, Option 1 using kubeadm, it'll take care of most things Option 1) set up your own cluster : set up your own cluster


#### 2. Availability and scaling: 
**Swarm**: Docker Swarm provides high availability as you can easily duplicate the microservices in Docker Swarm. Moreover, Docker Swarm has a faster deployment time. On the other hand, it doesn’t provide automatic scaling.
**Kubernetes**: Kubernetes is by nature highly available, fault tolerant, and **self-healing**. It also provides automatic scaling and can replace faulty pods if required.


#### 3. Load balancing: 
**Swarm**: Comes with internal load balancers.
**Kubernetes**: Discovery of services is enabled through a single DNS name. Kubernetes has access to container applications through an IP address or HTTP route.


#### 4. Monitoring:
**Swarm**: Docker Swarm supports monitoring only through third-party applications. There are no in-built monitoring mechanisms.
**Kubernetes**: In contrast, Kubernetes has built-in monitoring and supports integration with third-party monitoring tools.

#### 5. Security:
**Swarm**: Docker Swarm relies on transport layer security (TLS) to carry out security and access control-related tasks. 

**Kubernetes**: Kubernetes supports multiple security protocols such as RBAC, SSL/TLS, secrets management, policies, and so on.

