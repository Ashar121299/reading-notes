## What is Serverless?

_*Serverless is a cloud application development and execution model that lets developers build and run code without managing servers, and without paying for idle 
cloud infrastructure.*_

### Serverless does not mean 'no servers'

_*there are most definitely servers in serverless computing. 'Serverless' describes the developer’s experience with those servers—they are are invisible to the 
developer, who doesn't see them, manage them, or interact with them in any way.*_

### Serverless is more than just FaaS

Function-as-a-service, or FaaS, is a cloud computing service that enables developers to run code or containers in response to specific events or requests,
without specifying or managing the infrastructure required to run to code.


1.Serverless databases and storage: Databases (SQL and NoSQL) and storage (particularly object storage) are the foundation of the data layer. A serverless approach to
these technologies involves transitioning away from provisioning “instances” with defined capacity, connection and query limits, and moving toward models that scale 
linearly with demand in both infrastructure and pricing.

2.Event streaming and messaging: Serverless architectures are well-suited for event-driven and stream-processing workloads most notably the open source Apache Kafka 
event streaming platform.

3.API gateways: API gateways act as proxies to web actions and provide HTTP method routing, client ID and secrets, rate limits, CORS, viewing API usage, viewing
response logs, and API sharing policies.

### Serverless vs. PaaS, containers, and VMs

Because serverless, platform as a service (PaaS), containers, and virtual machines (VMs) all play a critical role in the cloud application development and compute
ecosystem, it’s useful to compare how serverless compares to the others across some key attributes.

1. Provisioning time: Measured in milliseconds for serverless, vs. minutes to hours for the other models.

2.Administrative burden: None for serverless, compared to a continuum from light to medium to heavy for PaaS, containers and VMs respectively.

3.Maintenance: Serverless architectures are managed 100% by the provider. The same is true for PaaS, but containers and VMs require significant maintenance 
including updating/managing operating systems, container images, connections, etc.

4.Scaling: Auto-scaling—including auto-scaling to zero—is instant and inherent for serverless. The other models offer automatic but slow scaling that requires
careful tuning of auto-scaling rules, and no scaling to zero.

5.Capacity planning: None needed for serverless. The other models require a mix of some automatic scalability and some capacity planning.

6.Statelessness: Inherent for serverless, which means scalability is never a problem; state is maintained in an external service or resource. PaaS, 
containers and VMs can leverage HTTP, keep an open socket or connection for long periods of time, and store state in memory between calls.

7.High availability (HA) and disaster recovery (DR): Both are inherent in serverless with no extra effort and at no additional cost. The other models require 
additional cost and management effort. In the case of both VMs and containers, infrastructure can be restarted automatically.

8.Resource utilization: Serverless is 100% efficient because there are no such things thing as idle capacity—it is invoked only upon request. All other 
models feature at least some degree of idle capacity.

9.Billing granularity and savings: Serverless is metered in units of 100 milliseconds. PaaS, containers and VMs are typically metered by the hour or the minute.


### Serverless, Kubernetes and Knative

Kubernetes is an open-source container orchestration platform that automates the deployment, management and scaling of containers. 

Knative provides a serverless framework for Kubernetes. It’s an open-source extension to Kubernetes that enables any container to run as a serverless workload
on any cloud platform that runs Kubernetes, whether the container is built around a serverless function or some other application code (e.g., microservices).



### Pros and cons of serverless


#### Pros

Given all of the preceding, it should be no surprise that serverless computing offers a number of technical and business benefits to individual developers
and enterprise development teams.

#### cons

With so much to like about serverless, organizations are using it for a wide variety of applications (see Figure 2 below). But there are drawbacks—some of which
are related to specific applications, and others which are universal.



### Use cases for serverless

#### Serverless and microservices

#### API backends

#### Data processing

#### Massively parallel compute/“Map” operations

#### Stream processing workloads

#### Common applications for serverless

