## Docker Swarm VS Kubernetes 
#### A brief intro of orchestration  
Orchestration is the automation of numerous tasks that run at the same time in a way that minimizes production issues and time to market.
**example of music conductor**

![dasd](https://user-images.githubusercontent.com/42219389/180896120-f31b716b-97c4-4b2f-8000-f068969c9bef.PNG)

#### What is Docker swarm?
![image](https://user-images.githubusercontent.com/42219389/181369027-9a137be9-3f85-4d8a-8161-73c04d80439b.png)
A swarm is a cluster of one or more computers running Docker. It can consist of one or more machines, so you can use swarm functionality on your local machine.
To create a swarm, run the `docker swarm init`
To join a swarm, `docker swarm join --token <token> <master-host>:<master-port> `

#### What is Kubernetes 
![image](https://user-images.githubusercontent.com/42219389/181372110-8e0d0fd4-b924-4036-815e-01abfc5c3cee.png)
A container orchestration platform for scheduling and automating the deployment, management, and scaling of containerized applications.
To get a token `kubeadm token list` or create one `kubeadm token create` 
To join a K8s cluster `kubeadm join <master-host>:<master-port>
--token <token>`





#### 1. Installation and setup:
**Swarm**: There is simple installation with Docker, and instances are typically consistent across operating systems.

**Kubernetes**: Manual installation can differ for each operating system. No installation is required for managed offerings from cloud providers.
- Setting up you own cluster is complex. Options: 
  1. Using kubeadm, it'll take care of most things 
  2. Set up your own cluster by installing each componenet seprately 

#### 2. GUI
 **Swarm**: Does not have a built-in dashboard. You need to integrate Docker Swarm with a third-party tool to get a GUI. Some of the most popular options are Portainer, Dockstation, Swarmpit, and Shipyard.

**Kubernetes**: Provides built-in dashboards via the Web UI, allowing a convenient way to control clusters and view statuses. 

#### 3. Load balancing: 
Docker Swarm offers automatic load balancing, while Kubernetes does not. However, it is easy to integrate load balancing through third-party tools in Kubernetes.
**Swarm**: Comes with internal load balancers and offers automatic load balancing
**Kubernetes**: Services are made discoverable through a single DNS name. Kubernetes accesses container applications through an IP address or HTTP route.


#### 4. Monitoring:
**Kubernetes**: Offers built-in logging and monitoring.. Vanilla K8s monitors app performance on two levels:
    - By inspecting individual services, pods, and containers.
    - By observing the behavior of an entire cluster.
As a K8s monitoring best practice, you should add a third-party tool to improve event-based monitoring. Here are some options:
    - ElasticSearch/Kibana.
    - InfluxDB.
    - Grafana.
    - Sysdig.

**Swarm**: Has basic server log and event tools from Docker, but these do not offer anything remotely close to K8s monitoring. You will likely need a third-party extension or app (InfluxDB, Grafana, cAdvisor, etc.) to meet monitoring needs.


#### 5. Scaling: 
Both K8s and Docker Swarm enable a user to quickly scale infrastructure up or down depending on current needs. 

**Swarm**: Requires users to perform scaling manually (via Docker Compose YAML templates). However, the platform is faster in deploying containers than what K8s can offer as there's no complex framework slowing scaling down.
**Kubernetes**: Has a feature for automated scaling that can self-adjust based on current traffic. K8s supports auto-scaling on both:
    - The cluster level (via Cluster Autoscaling).
    - The pod level (via Horizontal Pod Autoscaler).


#### 6. Security:
**Swarm**: Docker Swarm relies on transport layer security (TLS) to carry out security and access control-related tasks. 

**Kubernetes**: Kubernetes supports multiple security protocols such as RBAC, SSL/TLS, secrets management, policies, and so on.

Ref:
1. K8s on dropping Docker as a container runtime https://acloudguru.com/blog/engineering/kubernetes-is-deprecating-docker-what-you-need-to-know
2. Docker Swarm VS K8s https://phoenixnap.com/blog/kubernetes-vs-docker-swarm
3. Load balancing in Docker swarm https://blog.octo.com/en/how-does-it-work-docker-part-3-load-balancing-service-discovery-and-security/
4. How To Setup Kubernetes Cluster Using Kubeadm https://devopscube.com/setup-kubernetes-cluster-kubeadm/