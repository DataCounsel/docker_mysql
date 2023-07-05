
<H2 align="center">MySQL Database as a docker container on AWS EC2 instance</H2>


<p align="center">
<img src="https://github.com/DataCounsel/docker_mysql/assets/71335870/29a5e836-cbb5-45fd-b57f-b04f92691cd4">
</p>

### <ins>Project Objective</ins>

Using MySQL database as a docker container running in the cloud
In this project the aim is to replicate a business use case where developers can use a MySQL Docker instance from their local machine without the need to install a specific version and having an on-premises server. Docker containers are used for their numerous benefits:
1. Portability: Containers encapsulate applications and their dependencies, making them highly portable across different environments. They eliminate the "it works on my machine" problem by providing consistent behaviour across development, testing, and production.
2. Efficiency: Containers are lightweight and share the host system's OS kernel, enabling efficient resource utilization. Multiple containers can run on a single host, maximizing server efficiency and reducing hardware costs.
3. Isolation: Containers provide process-level isolation, keeping applications and their dependencies isolated from each other. This isolation enhances security, prevents conflicts between applications, and enables easier management of complex systems.
4. Scalability: Docker containers are designed to scale horizontally, allowing easy replication and distribution of application components across multiple containers or hosts. Containers can be rapidly deployed and scaled up or down as needed, ensuring optimal resource allocation.
5. Rapid deployment and version control: Containers enable quick and consistent application deployment. They package all the required dependencies, making it easy to deploy applications on any system that supports Docker. Furthermore, Docker allows versioning of container images, enabling efficient rollback and roll-forward procedures.
6. DevOps integration: Docker containers fit well into DevOps workflows, facilitating continuous integration, continuous delivery (CI/CD), and automated testing. Containers can be easily integrated with tools like Kubernetes, Jenkins, and Git, streamlining the development and deployment process.
Overall, Docker containers simplify application deployment, enhance scalability and portability, improve resource utilization, and promote DevOps practices, making them a popular choice for modern software development and deployment. 
For the purpose of this project, I am using AWS as the cloud provider and using an EC2 instance running Amazon Linux 2 for installing and running the Docker containers. MySQL version 8.0.33 which is tagged latest at the time of writing this was used.


#### Docker container created with docker ports mapped to local ports 
![image](https://github.com/DataCounsel/docker_mysql/assets/71335870/16c6ea40-e2b5-4817-9e07-3ebcaa57a700)

Mapping the ports of the Docker instance with the local EC2 instance allows the MySQL instance to be accessed from local computer.  

![image](https://github.com/DataCounsel/docker_mysql/assets/71335870/48c2c475-7ee1-4605-8a54-bb70bc530552)

The Docker volume has been mounted to the local system to enable persistence of the data. This ensures the data would be unaffected in case a container is terminated or lost

![image](https://github.com/DataCounsel/docker_mysql/assets/71335870/c8f0c000-6a90-411e-a78e-b89995997d30)

The details of the MySQL database running as a container 

![image](https://github.com/DataCounsel/docker_mysql/assets/71335870/0ce8e6d3-1e02-4c82-81c5-701f52aca52a)

A new user Debrup is created and is granted all privileges as the root user

![image](https://github.com/DataCounsel/docker_mysql/assets/71335870/f197044a-3f5a-4389-a6c1-cda6ed19fa55)

Logged into MySQL inside the container instance and we can see the databases present in MySQL

![image](https://github.com/DataCounsel/docker_mysql/assets/71335870/1a0a5af0-c046-4d65-8016-a2d955438fb6)

A table ‘Employee’ is created and it can be seen it is stored in the locally mounted volume. This demonstrates that the persistence is achieved and data will remain unaffected even if the container instance is terminated

![image](https://github.com/DataCounsel/docker_mysql/assets/71335870/ee03c4cd-2231-4add-85f3-3c8475bb78c3)

This image shows that the host MySQL instance was successfully connected from the local machine using Windows Command prompt and using user Debrup

This project is a demonstration of how a docker container can be used in the day-to-day scenario in the workplace.







