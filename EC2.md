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

  1. General Purpose :
     - Diversity of workload 
     - Balance between Memory, Networking, Compute
     - eg : t2.micro

  2. Compute Optimized : 
     - Great for compute intense task that needs high performance processors like web servers, gaming servers.
     - eg : c6g, c5

  3. Memory Optimized :
     - Fast performance to process large data set in the memory (RAM)
     - eg : r5, r4

  4. Storage Optimized :
     - Great for storing large data sets in the local storage that requires high read and write operations.  
     - eg : d4, d5, i3

 ### Security Groups 
  - Security groups only contain "ALLOW" rules
  - Security groups are acting as a firewall on EC2 instances
  - The rules of Security groups can reference by IP or by security group
  - It regulates : 
     - inbound/ outbound network
     - port access
     - authorised IP ranges 
  - One security group can be attached to multiple EC2 instances 
  - All inbound traffic is blocked by default
  - All outbound traffic is authorised by default
  - Security groups are attached outside the EC2 instance so the blocked access can't be known to the EC2 instance 
  - Application not accessible (time out) --> security group issue 
  - Connection refused error in application --> network issue/ application issue
  - A security group created in one region cannot be used in another region
  - A security group created in one VPC cannot be used in another VPC
  
 ### EC2 Instances Purchasing Options
  - On-demand instance
  - Reserved instance
  - Spot instance
  - Savings plan 
  - Dedicated host 
  - Dedicated instance
  - Capacity reservation

  1. On-demand Instance
     - Rent instantly
     - Pay per secons/hour 
     - For short term use

  2. Reserved Instance
     - Reserve for a period of 1 to 3yrs in advance
     - It is you commit to use an instance for a particular period of time on the AWS
     - For long term use
     - Can be cheaper than on-demand
     - Eg : I will use this exact server type for 1–3 years (Production Servers)

  3. Spot Instance 
     - You can get an instance at the spot by announcing the price higher than the current value of the instance 
     - It is not reserved for you, AWS can take it anytime like when another user gives higher value than your value for the instance 

  4. Saving plan
     - Same like reserved instance but you commit for the amount spending for a period of time on the AWS
     - For long term use
     - Eg : I will spend ₹500 per hour, but I may use different servers

  5. Dedicated Host 
     - you control the entire physical server
     - You can have the control of your instance and the hardware that runs the instance 
     - Eg : Like renting full customized server to run your instance on it  

  6. Dedicated Instance 
     - You can have full control of the instance but You don’t control or see the physical server
     - AWS manages the physical server 
     - Eg : You want isolation (no other customers on same hardware), but don’t care about hardware details 

  7. Capacity Reservation
     - AWS will always keeps capacity ready for you, reserving a room so it’s always available to you
     - It is same like On-demand pricing 
     - Eg : You need 10 servers during a big event → reserve capacity → no risk of “out of stock”.
 
 ### Spot Fleets
  - Spot Fleets = set of Spot Instances + (optional) On-Demand Instances
  - A Spot Fleet is just a smart manager that launches multiple Spot Instances for you when you ask for it
  - Launch pool --> provides different options to the spot fleet 
     - It is the combination of : 
        - instance type
        - availability zone
        - OS
  - Spot fleet stops when the required capacity is reached 
  - Allocation Strategies : This is how spot fleet chooses instance 
     - Lowest price : chooses the cheap instance
     - diversified : chooses instance across many pools 
     - capacityoptimized : picks pools with most available capacity (how many EC2 instances AWS can currently provide from that pool)
     - price capacity optimized : high capacity + low price (real-world use case)
