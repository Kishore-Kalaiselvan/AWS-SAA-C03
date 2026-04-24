### What is Ec2
 - EC2 is a region based service it is not available in all region 
 - It is a IaaS (Infrastructure as a Service)
 - It mainly consists in the capability of :
    - Renting virtual machines (EC2)
    - Storing data on virtual drives (EBS)
    - Distributing load across machines (ELB)
    - Scaling the services using an auto-scaling group (ASG)

 ### Types of cloud computing 
 In Simple
   1. IaaS - Infrastructure as a Service 
  - All the component required for building a server/service will be given, the user can customize their server with those component
  for example : all the raw materials for constructing a building will be given, using all those given raw materials you can construct the building for your requirement it is IaaS.
   2. PaaS - Platform as a Service
  - The server/service will be given to you using that server/service you can deploy or host an application or store a data whatever you want to do with the service
  for example : The whole building will be constructed and given to you, with the given building you can use it effectively as a home or a office like that
   3. SaaS - Software as a Service 
  - The whole product will be given to the user, the user can just use the product for their own use cases
  for example : Applications like gmail, drive will be given to users they can use these products for their own uses.

 ### EC2 Configuration:
  - The user can configure 
      - OS
      - RAM
      - instance type
      - CPU 
      - Firewall: security group 
      - Storage : Network attached (ELB/EFS) and Hardware (EC2 instance store)

 ### EC2 User Data
  - It is the user given data or instructions that runs only once that too for the first time of the machine starting after launching the ec2 instance 
  - It is called as bootstrapping - means launching commands when a machine starts
  - Those data/instructions are called as scripts 
  - These user data are used to automate boot tasks such as :
     - Installing updates
     - Installing softwares 
  - These data runs with the root user 

 ### EC2 Instance Types:
  - m5.2xlarge
    - m --> instance class
    - 5 --> generation of the instance class
    - 2xlarge --> size of the instance 

   1. General Purpose 
     - Diversity of workload 
     - Balance between Memory, Networking, Compute
     - eg : t2.micro

   2. Compute Optimized 
     - Great for compute intense task that needs high performance processors like web servers, gaming servers.
     - eg : c6g, c5

   3. Memory Optimized 
     - Fast performance to process large data set in the memory (RAM)
     - eg : r5, r4

   4. Storage Optimized 
     - Great for storing large data sets in the local storage that requires high read and write operations.  
     - eg : d4, d5, i3
