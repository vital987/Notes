# AWS Certified Solutions Architect Associate
*	 Table of contents: 
	*	[Regions & Availability Zones](#regions-&-availability-zones)
	*	[IAM](#iam)
	*	[EC2](#ec2)
	*	[EFS](#efs)
	*	[RDS](#rds)	
##	**AWS:** Amazon Web Services, a leading cloud provider.
## Regions & Availability Zones
*	**Regions & Availability Zones aka. AZ:** Region is a cluster of AZ whereas AZ is a single data center.
	*	Most of the AWS services are region-scoped.
	*	**Factors for choosing AWS region:**
		*	**Compliance of data governance & legal requirements:** Data never leaves a region without your explict permission.
		*	**Proximity to customers:** Reduced latency.
		*	**Availability of services:** All services aren't available in all regions.
		*	**Pricing:** Pricing varies based on regions.
	*	Each region has usually 3 availability zones, minimum 2 & maximum 6.
	*	Regions are named as Eg: Sydney: ap-southeast-2, & it's AZ are named as ap-southeast-2a, ap-southeast-2b, etc
	*	AZ are separate from each other to keep isolated from disasters.
	*	All AZs within a region are connected with high bandwidth forming a region.
## IAM
*	**IAM aka. Identity Access Management:** Used to set & modify access permissions and roles.
	*	**Service:** Global
	*	**Root account:** Created by default, shouldn't be used or shared.
	*	**Users:** People within your organization, a user can belong to multiple groups.
	*	**Groups:** Group of users, a group cannot contain another group.
	*	**Policies:** Permissions for user to access services, is written in JSON format, or can be made using visual editor.
	*	**Least Privilege Principle:** Don't give more permissions than a user needs.
	*	**Protecting users & groups from being compromised:** 
		*	**Password Policy:** Requirements for applying a password to account eg: should contain alpha-numeric with symbols, password expiration, etc.
		*	**MFA:** Multi-Factor Authentication
			*	**Types of MFA:**
				*	**Virtual MFA:** Eg: Google Authenticator, MS Authenticator, Authy, etc
				*	**Universal 2nd Factor (U2F) Security Key:** Physical Device Eg: Yubikey.
				*	**Hardware Key Fob MFA Device:** Eg: Gemalto, SurePassID for AWS GovCloud.
	*	**Their are 3 ways to access AWS account:** 
		*	**AWS Management Console**: Protected by Password & MFA.
		*	**AWS CLI**: Protected by access keys.
		*	**AWS SDK**: Protected by access keys.
	*	**Access Keys:** 
		*	Can be generated through Management Console.
		*	Users manage their own access keys.
		*	When creating access keys we get: Access Key ID ≅ Username & Secret Access Key ≅ Password.
	*	**IAM Roles:** IAM entity that defines a set of permissions for making AWS service requests, that will be used by AWS services.
	*	**IAM Audit Tools:** 
		*	**IAM Credentials Report (account-level):** Report which lists out all users from the account with their various status.
		*	**IAM Access Advisor (user-level):** Shows service permissions granted to a respected user and when those services were last accessed.
	*	**IAM Guidelines & Best Practices:** 
		*	Don't use root user except for AWS account setup.
		*	One Physical User = One Separate AWS User.
		*	Assign users to groups and try managing permissions at group level.
		*	Create a strong password policy.
		*	Use & enforce the use of MFA.
		*	Create roles for services instead giving access keys.
		*	Use access keys for programmatic access (CLI/SDK).
		*	Audit permissions of the account with IAM Security Tools.
		*	Never share IAM user & Access keys with anyone.
## EC2
*	**EC2 aka. Elastic Compute Cloud:** Scalable virtual machines.
	*	**Service:** Regional
	*	**Supported OS:** 
		*	Linux
		*	MacOS
		*	Windows
	*	**User Data:** Bootstrap script (runs on instance boot-up), runs with the root user.
	*	**Instance:** Single VM.
		*	**Naming Convention:** t3.micro - t=instance-class, 3=generation, micro=size within instance class.
		*	**Types:** 
			*	**General Purpose:** Balanced compute, memory & networking resources.
			*	**Compute Optimized:** Higher compute ratio.
				*	***Use cases:*** 
					*	Batch Processing Workloads.
					*	Media Transcoding.
					*	High performance web servers.
					*	High Performance Computing (HPC).
					*	Scientific modelling & machine learning.
					*	Dedicated gaming servers.
			*	**Memory Optimized:** Higher memory ratio.
				*	***Use cases:*** 
					*	High performance relational/non-relational databases.
					*	Distributed web scale cache stores.
					*	In-memory databases optimized for Business Intelligence (BI).
					*	Applications performing real-time processing big unstructured data.
			*	**Storage Optimized:** Higher storage ratio.
				*	***Use cases:*** 
					*	High processing online transaction (OLTP) systems.
					*	Relational & NoSQL databases.
					*	Cache for in-memory databases (Eg: Redis).
					*	Data warehousing applications.
					*	Distributed file systems.
			*	**Acclerated Computing:** Acclerated computing instances.
				*	***Use cases:***
					*	Graphic intensive processing
					*	For intensive calculations such as floating point number calculations.
					*	Data Patterns
	*	**[ ! ]** Public IP changes when the instance is restarted.
	*	**Purchasing options:** 
		*	**On-Demand Instances:** 
			*	Pay per hour/second.
			*	No commitments.
			*	Has the highest cost.
			*	No upfront payment.
			*	Recommended for short-term & un-interrupted workloads where the future instance behaviour is not predictable.
		*	**Reserved:** 
			*	**Reserved Instances:** Longer Workloads.
				*	Upto 72% discount compared to On-Demand instances.
				*	Reservation period: 1 Year or 3 Years.
				*	Larger reserve duration = bigger discounts.
				*	Payment options: No upfront = No discount(on upfront), Partial upfront = Discount, Full Upfront = Bigger discount
				*	Recommended for steady-state applications eg: Databases.
				*	Fixed instance families, operating system, tenancy, and payment option.
			*	**Convertible Reserved Instances:**
				*	Less discounts than normal reserved instances.
				*	Changable instance families, operating system, tenancy, and payment option.
			*	**Scheduled Reserved Instances:** Scheduled for specific time, Eg: Every day between 10:00 to 19:00.
			*	**Spot Instances:** Short workloads, cheap, less reliability (can often lose them).
				*	Most cost efficient instances, upto 90% off compared to on-demand instances.
				*	Non-reliable, can be lost at any point of time if your max bidded instance price is less than the current spot price.
				*	If current spot price > bidded price, their is a 2 minutes of grace period before the instance stops.
				*	**Spotblock:** "Block" spot instance for a specific time period (1 to 6 Hours) without interruptions.
					*	In rare conditions, the instance may get reclaimed.
				*	**Spot Requests:** Request made to buy spot instances, contains 
					*	**One-time Request:** The request gets expired when it is fulfilled.
					*	**Persistant Request:** The request is not expired till a manual cancellation.
						*	 In this case if an instance gets reclaimed, another spot instance will be issued if the spot price goes below the user max price.
					*	Spot requests can be cancelled only if they are in open, active or disabled state.
					*	Cancelling spot requests does not terminate instances, manual termination is required.
				*	**Spot Fleets:** Set of Spot instances + On-Demand instances (optional)
					*	A Spot Fleet will try to meet the largest request capacity with the price constraints.
					*	Can have multiple pools to provide choices for Spot Fleet.
					*	Will stop launching requests when the specification is met or the price limit is maxed out.
					*	Allocation strategies: 
						*	**Lowest Price:** Chooses from the pool with lowest price (cost optimization, shorter workloads)
						*	**Diversified:** Distributed across all available pools (great availability, longer workloads)
						*	**Capacity Optimized:** Pool with optimal capcity for the number of instances.
				*	***Use cases:*** 
					*	Batch jobs.
					*	Data analysis.
					*	Image processing.
					*	Distributed workloads.
					*	Workloads with flexible start & end time.
					*	**[ ! ]** Never run critical jobs & databases on these instances.
			*	**Dedicated Hosts:** Entire physical server with EC2 instance capacity.
				*	Can help with compliance requests and reduce costs by using existing software licenses.
				*	Visibility of sockets, cores, host ID
				*	Targeted instance placement
				*	Can add capacity using an allocation request.
				*	Per host billing.
				*	Useful for the software that has complicated license model (BYOL - Bring Your Own License)
			*	**Dedicated Instances:** Instance that runs on a physical server but the server is shared with other instances.
				*	Per instance billing(subject to $2 per region fee).
			*	**[ * ]** Prices & Discounts can be calculated [here](https://aws.amazon.com/ec2/pricing/reserved-instances/pricing/)
	*	**Security Groups:** Virtual firewall for your instance to control inbound and outbound traffic.
		*	Can be attached to multiple instances.
		*	**Regulates:** 
			*	Access to ports
			*	Authorized IP ranges, IPv4 & IPv6
			*	Control of inbound network (from other to instance)
			*	Control of outbound network (from instance to other)
		*	**Region specific:** Needs a new security group for new region.
	*	**IP Addresses:** 
		*	**Public:** Changes on every instance restart (not reboot).
		*	**Private:** Internal IP of AWS network, used to connect to services internally.
		*	**Elastic IP:** A static IP address that never changes till we rent it.
			*	Limited to 5 IPs per account, one can ask AWS to increase the limit.
			*	**Advice:** Try avoiding elastic IPs, rather assign a DNS to the public IP, or use loadbalancer to prevent usage of public IP.
	*	**Placement Groups:** Controls the placement of instances within AWS infrastructure.
		*	**Strategies:** 
			*	**Cluster:** Clusters instances in a low-latency group in a single availability zone.
				*	**Placement:** Single Rack, Same AZ.
				*	***Pros:*** 
					*	Great network (10Gbps bandwidth between instances).
				*	***Cons:*** 
					*	High failure risk cause all instances are placed on single rack.
				*	***Use cases:***
					*	Big data job that needs to complete fast.
					*	Applications needing extremely low-latency & high network throughput.
			*	**Spread:** Each instance on different hardware.
				*	***Pros:*** 
					*	Low risk of failure.
					*	Can span accross AZs.
				*	***Cons:*** 
					*	Limited to 7 instances per group.
				*	***Use cases:*** 
					*	Critical applications which needs high-availability.
			*	**Partition:** Instances are placed on different partitions(group of server racks within AZ) accross AZs.
				*	***Pros:***
					*	Can span across multiple AZs within a region.
					*	The instances in a partition do not share racks with the instances in other partitions.
					*	EC2 instances get access to the partition information as metadata.
				*	***Cons:*** 
					*	Limited upto 7 partitions per AZ
				*	*****Use cases:***** 
					*	Big data applications such as Hadoop, Kafka, Cassandra.
	*	**ENI aka. Elastic Network Interface:** Logical component in a VPC representing a virtual network card.
		*	Master/Primary private IPv4 and multiple secondary IPv4.
		*	One elastic IP(IPv4) per private IPv4.
		*	One public IPv4.
		*	Bound to specific AZ.
		*	Can be created independently and later be attached to instance.
		*	Can be moved between instances.
	*	**EC2 Hibernate:** Hibernation of EC2 instances.
		*	In-memory state is preserved.
		*	**Process:** Memory state is dumped into a file on root EBS volume > Instance is stopped
		*	Boot-up after hibernation is much faster.
		*	The root volume must be EBS, encrypted, instance store volumes are not supported.
		*	Only supports C, M & R families (may change in future).
		*	RAM size should be less than 150GB.
		*	Not supported for bare-metal instances.
		*	Only available for On-Demand & Reserved Instances.
		*	Can be hibernated only upto 60 days.
		*	***Use cases:*** 
			*	Long-running processes.
			*	Preserving RAM state.
			*	Prevent long-initializing service from re-initializing.
	*	**EC2 Nitro:** Underlying platform for next generation EC2 instances.
		*	New virtualization technology.
		*	Better networking options (enhanced networking, HPC, IPv6)
		*	Higher EBS speeds (Max. 64,000 IOPS compared to non-nitro speeds i.e. 32,000 IOPS).
	*	**EC2 vCPUs:** vCPU = 1 Thread of a core of a CPU.
		*	**Example:** m5.2xlarge
			*	4 CPUs
			*	2 Threads per CPU
			*	4 * 2 = 8 vCPUs
		*	We can decrease number of CPU cores and threads in some instances as per requirements.
	*	**Capacity Reservations:** Reserve a specific amount of computing capacity for specific number of instances and duration with other specs(os, instance type, etc) in a specific AZ.
		*	Only supported by linux and linux+db platforms.
		*	Active and unused Capacity Reservations count toward your On-Demand Instance limits.
		*	Can't be created in placement groups.
		*	Can't be used with Dedicated Hosts.
		*	Do not ensure that a hibernated instance can resume after you try to start it.
	*	**EBS aka. Elastic Book Store volume:** An EBS volume is network drive that you can attach to EC2 instances.
		*	**Service:** Regional
		*	**Volume types:** 
			*	**General Purpose:** gp2, gp3
				*	**Volume Size:** 1GiB to 16TiB
				*	**IOPS:** gp2: Constant Baseline: 3IOPS/GiB , Burstable:3000IOPS | gp3: Baseline: 3IOPS/GiB , Burstable:3000IOPS
				*	**Max **Throughput:* gp2: 250 MiB/s (16KiB I/O) | gp3: 1000 MiB/s (16KiB I/O)
				*	**Boot Volume:** Yes
			*	**IOPS Provisioned:** io1, io2, io2 block express
				*	**Volume Size:** io1, io2: 4GiB to 16TiB | io2 block express: 4GiB to 64TiB
				*	**IOPS:** Min: 100, Max: 64000 | io2 block express: Max: 256,000
				*	*Throughput:* io1, io2: 1000MiB/s | io2 block express: 4000MiB/s
				*	**Boot Volume:** Yes
				*	****Use cases:**** 
					*	**io1, io2:** 
						*	Workloads that require sustained IOPS performance or more than 16,000 IOPS.
						*	I/O-intensive database workloads
					*	**io2 block express:** 
						*	Workloads that require sub-millisecond latency, sustained IOPS performance or more than 64,000 IOPS or 1,000 MiB/s of throughput.
				*	**Multi-attach support:** Connect to multiple EC2 instances within same AZ.
					*	Must use filesystem that is cluster aware eg: IBM Tivoli SANergy, RedHat GFS, IBM GPFS.
					*	**Use case:** To achieve higher application availability in clustered linux applications eg: Teradata.
			*	Throughput Optimized HDD: st1
				*	**Volume Size:** 125GiB to 16TiB
				*	Max **IOPS:** 500 (1MiB I/O)
				*	**Throughput:** 500MiB/s
				*	**Boot Volume:** No
				*	****Use cases:**** 
					*	Big Data
					*	Data Warehousing
					*	Log Processing
			*	**Cold HDD:** sc1
				*	**Volume Size:** 125GiB to 16TiB
				*	Max **IOPS:** 250 (1MiB I/O)
				*	**Throughput:** 250MiB/s
				*	**Boot Volume:** No
				*	****Use cases:**** 
					*	Infrequently accessed data
					*	For cheapest cost scenarios
		*	Allows data persistance after instance termination.
		*	They can be mounted on only one instance at a time(at Cloud Practitioner level).
		*	Bound to specific AZ.
		*	Have provisioned capacity.
		*	**Delete on termination:** When creating EC2 instances, we have choice to delete EBS volume when the instance is terminated.
			*	By default EC2 root EBS volume is enabled for DOT, can be disabled.
		*	They are available as block devices, so for linux based instances we need to make partition table, format the block device, create filesystem and then mount it.
		*	**EBS Snapshot:** Backup of EBS volume.
			*	Not necessary to terminate instance & detach the volume to do snapshot, but it's recommended.
			*	Can copy snapshots over AZs and regions.
		*	**EBS Encryption:**
			*	Data inside EBS volume is encrypted encrypted using AES-256 algorithm.
			*	The data flight moving between EBS volume and EC2 instance is also encrypted.
			*	Snapshots created from EBS volume are also encrypted.
			*	All volumes created from the snapshot are also encrypted.
		*	EBS supports RAID, but user needs to configure raid on OS.
	*	**AMI aka. Amazon Machine Image:** Customization for EC2 Instances.
		*	Can install custom softwares and configure base images as per the consumer needs.
		*	Faster boot due to pre-installation of requisites.
		*	Built for a specific region and can be copied across regions.
		*	**Types:** 
			*	**Public AMI:** AWS managed AMIs.
			*	**Custom AMI:** User created AMIs so also needs to be managed by the user only.
			*	**AWS Marketplace AMI:** Premium AMIs sold by different software vendors.
		*	**Steps to create AMI:** 
			*	Create an EC2 instance and customize it as per user needs.
			*	Stop the instance(for data integrety).
			*	Build the AMI(also creates ebs snapshots behind scenes).
			*	Launch other instances from the built AMI.
	*	**EC2 Instance Store:** Ephemeral hardware disk.
		*	Fast I/O speeds.
		*	**Ephemeral:** Looses data on instance restart.
		*	Good for buffer, cache, temporary files, scratch data, etc.
		*	Risk of data loss if hardware fails.
	*	**LoadBalancers:** Distributes the traffic among multiple instances to reduce the instance loads.
		*	High Availability & Scalability: 
			*	**Vertical scaling:** Increasing/Decreasing the size of instance aka. scale-up/scale-down.
			*	**Horizontal scaling:** Increasing/Decreasing the number of instances aka. scale-in/scale-out.
			*	**High Availability:** Ability to survive disasters eg: data-center powerloss, data-corruption, etc.
		*	**Features:** 
			*	Distributes loads accross multiple underlying instances.
			*	Exposes single point of access(DNS or IP) to the application.
			*	Seamlessly handle failures of the instances.
			*	Enforces stickiness with cookies.
			*	High availablity across zones.
			*	Separates public traffic from private traffic.
		*	**Types:** 
			*	**CLB aka. Classic LoadBalancer(v1-2009):** HTTP, HTTPS, TCP
				*	Layer-4 & layer-7 loadbalancer.
			*	**ALB aka. Application LoadBalancer(v2-2016):** HTTP, HTTPS, WebSockets
				*	Layer-7 loadbalancer
				*	LoadBalancing to multiple HTTP applications across machines.
				*	Loadbalancing multiple applications on a same machine.
				*	Routing tables to different target groups based on: 
					*	**Path URL Eg:** https://example.com/one, https://example.com/two
					*	**Hostname Eg:** https://one.example.com, https://two.example.com
					*	**Query strings Eg:** https://example.com?id=1, https://example.com?id=2
				*	Great for micro-services & container-based applications.
				*	Health checks are done at the target-group level.
				*	Fixed hostname (xxx.region.elb.amazonaws.com)
				*	The application servers(servers behind ALB) don't see the IP of the client directly, instead they are inserted in the headers, some examples are: 
					*	**X-Forwarded-For**: Client's IP address.
					*	**X-Forwarded-Port**: Client's IP Port.
					*	**X-Forwarded-Proto**: Client's IP Protocol.
			*	**NLB aka. Network LoadBalancer(v2-2017):** TCP, TLS, UDP
				*	Layer-4 LoadBalancer.
				*	Can handle millions request per second.
				*	Less latency ~ 100ms (vs ALB ~400ms~)
				*	Has 1 static IP per AZ pre-assigned, supports elastic IPs.
				*	Static IP/Elastic IP.
		*	**Stickiness:** Always redirect a client to the same instance behind the loadbalancer, works with CLB & ALB.
			*	Works by creating a cookie on client-side with an expiration date the user can control.
			*	Enabling it may bring imabalance in the load on the instances.
			*	**Use case:** Prevent loss of user's session data.
		*	**Cross-Zone loadbalancing:** Traffic is shared among instances located across AZs.
			*	**ALB:**
				*	Always on.
				*	No charges incurred for inter-AZ data transfer.
			*	**NLB:** 
				*	Disabled by default.
				*	Charged are incurred for inter-AZ data transfer.
			*	**CLB:** 
				*	Enabled by default if created through console.
				*	Disabled by default if created through CLI/SDK.
				*	No charges incurred for inter-AZ data transfer.
		*	**SNI aka. Server Name Indication:** Helps to load multiple SSL certificates for multiple websites running on same web-server.
			*	It's a new protocol & requires the client to specify the hostname of the target server in the initial SSL handshake.
			*	The server will find the default certificate and return the default one.
			*	Only works with ALB, NLB & Cloudfront.
		*	**Connection Draining(CLB) aka. Deregistration Delay(Target Group):** Time to complete the in-flight requests while the server instance is unhealthy/terminating(draining).
			*	Deregistration delay can be set from 0(disabled) to 3600 seconds(1 hour).
		*	**ASGs aka. Auto-scaling groups:** Automatically scales (add/remove) EC2 instances according to the load.
			*	Scales-in (removes instances) when the load is decreased.
			*	Scales-out (adds instances) when the load is increased.
			*	Can automatically register newly created instances to the loadbalancer.
			*	Scaling policies can be CPU usage, Network usage, custom metrics from Cloudwatch, Cloudwatch alarms, etc.
			*	ASG directly terminates the instances if stated unhealthy & creates new ones.
			*	Free.
			*	**Scaling Policies:**
				*	**Target tracking scaling:**
					*	**Example:** If user sets the CPU usage around 40%, ASG will scale down when the usage is critically below 40 and vice-versa.
				*	**Simple/Step Scaling:** Taking actions based on Cloudwatch alarms.
					*	Eg: When a Cloudwatch alarm is triggered (eg: CPU Usage > 70%) then add 2 instances.
					*	Has more control over scaling of instances.
				*	**Scheduled Actions:** Scaling instances based on time durations.
					*	**Example:** Scale-up to 10 instances on Fridays from 17:00 to 22:00.
			*	**Scaling cooldown:** A cooldown period to ensure that your ASG dosen't launch/terminate any instances before the previoud scaling activity takes place.
				*	Can create custom cooldown periods that apply to specific simple scaling policy.
				*	One can reduce costs by reducing default scale policies.
			*	**Default termination policy:** 
				1.	Find AZ with greater number of instances.
				2.	If their are multiple instances in AZ, then choose the on with oldest configuration.
				*	ASG Tries to balance instances across AZs.
			*	**Lifecycle Hooks:** 
				*	By default when instance is launched by ASG, it is directly in *inService* state.
				*	ASG have ability to perform extra steps before getting the instance in *inService* state i.e. *pending:wait*&*pending:proceed* state.
				*	ASG have ability to perform extra steps before getting the instance in *terminating* state i.e *terminating:wait*&*terminating:proceed* state.
				*	**Process:** ASG launched/terminated an instance > *pending/terminating:wait* > extra steps > *pending/terminating:proceed* > *inService*/*terminated*
				*	**Use case:** Extract logging information from an instance before it is terminated.
		*	**Troubleshooting:** 
			*	**Error 4xx:** Client induced errors
			*	**Error 5xx:** Application induced errors
			*	**LB Error 503:** Targets aren't registered or overloading.
		*	**Monitoring:** 
			*	ELB access log will log all the requests.
			*	Cloudwatch metrics will give aggregate statistics.
## EFS
*	**EFS aka. Elastic File System:** A managed network file system which can be attched to multiple EC2 instances across AZs.
	*	Highly available.
	*	Scalable.
	*	Expensive(3x gp2), can leverage EFS-IA for some cost-savings.
	*	Pay-per-use.
	*	Uses NFS v4.1 protocol.
	*	Uses security group for access control.
	*	EFS only supports linux!
	*	Encryption support.
	*	Auto-scaling.
	*	10GiB+/s throughput.
	*	**Performance mode:** 
		*	General purpose(default): Latency sensitive use cases (web-server, CMS, etc)
		*	Max I/O: Higher latency, better throughput, highly parallel (big data, media processing)
	*	**Throughput mode:** 
		*	**Bursting:** 1TB=50MiB/s + burst upto 100 MiB/s
		*	**Provisioned:** Independantly set your throughput regardless of storage size.
	*	**Storage Tiers (lifecycle management feature - move files after x days):**
		*	**Standard:** For frequently accessed files.
		*	**Infrequent access(EFS-IA):** cost to retrieve files, lower price to store.
	*	****Use cases:**** 
		*	Content management
		*	Web serving
		*	Data sharing
## RDS
*	**RDS aka. Relational Database Service:** Managed database service.
	*	**Service:** Regional
	*	Allows to create databases in the cloud, managed by AWS.
	*	Supported engines: 
		*	Amazon Aurora
		*	MySQL
		*	Oracle
		*	Postgres
		*	MariaDB
		*	Microsoft SQL Server
	*	Services provided on the top of RDS: 
		*	Automated OS provisioning
		*	Continues backups & restores, os user can rollback to specific timestamp, also called as Point in Time Restore.
		*	Monitoring dashboards.
		*	Read replicas for improved read performance.
		*	Multi-AZ setup for disaster recovery.
		*	Maintainence windows for upgrades.
		*	Scaling capability(vertical & horizontal)
		*	Storage backed by EBS (gp2 or io1) volumes.
		*	You can't SSH into the database server.
	*	**Backups:** 
		*	Daily full backup of the database.
		*	Transaction-logs are backed-up by RDS every 5 minutes.
		*	7 days retention of the backup, can be extended upto 35 days.
		*	**DB Snapshots:** Manual backups triggered by the user, no limit on retention on the backup.
		*	**RDS Storage Scaling:** Auto-scaling the database dynamically.
		*	**Automatically expand storage if:** 
			*	Free storage is less than 10% of the available storage.
			*	If the above state lasts for more than 5 minutes.
			*	6 Hours has passed since last modification.
			*	**Use case:** Unpredictable workloads.
	*	**Read Replicas:** Separate DB instances that are synced asynchronously with the Master/Primary database, which has only read premissions.
		*	Can be in the same AZ, cross-AZ, cross-Region.
		*	Can create upto 5 Read Replicas.
		*	Replication between the Master/Primary DB and replica DB is asynchronous so the reads are consistant.
		*	Can be promoted to their own DB(with read/write access).
		*	Application must consider the read replicas for the connection.
		*	is read-only and therefore can run only SQL-readonly commands.
		*	**Network cost:** 
			*	Unlike other services, for inter-AZ data transfer, no charges are occured.
			*	For inter-region, charges are applied.
	*	**Multi-AZ:** A standby DB is created in different AZ for disaster recovery, and automatic failover is made when the Master/Primary DB access fails.
		*	**Standby DB:** A synchronous DB replica without read & write access(except the access to the Master/Primary DB).
		*	Cannot be used for scaling.
		*	No manual intervention needed.
		*	Internal process: Takes snapshot of Master/Primary DB > Creates a Standby DB > Loads the snapshot onto the Standby DB > Synchronization is established between two DBs.
	*	**Encryption:** Supported
		*	**Data at Rest Encryption:** 
			*	TDE(Transparent Data Encryption) supported for Oracle & SQL server.
			*	Replica/Standby DBs cannot be encrypted without encrypting Master/Primary DB.
		*	In-flight Data Encryption:
			*	SSL certificates are used.
			*	To enforce SSL: 
				*	PostgreSQL: rds.force_ssl=1 in RDS parameter group.
				*	MySQL: Within DB, run: *GRANT USAGE ON \*.\* TO 'mysqluser'@'%' REQUIRE SSL;*
		*	Encrypting unencrypted DB: 
			1.	Take snapshot of unencrypted DB.
			2.	Make a copy of the snapshot into an encrypted snapshot.
			3.	Create a new DB from the encrypted snapshot.
			4.	Migrate to the new DB.
	*	**Network Security:** 
		*	RDS are usually deployed within private subnet.
		*	Leverages security groups for protection.
	*	**Access Management:**
		*	Leverages IAM policies.
		*	IAM-based authentication can be used for MySQL & PostgreSQL.
		*	**IAM-based Authentication:** 
			*	Authentication is based on a token generated by IAM using RDS API calls which is valid for 15 minutes.
				*	No DB login password is needed if enabled.
	*	**Amazon Aurora:** AWS proprietary DB service.
		*	Supported as replacements MySQL & PostgreSQL DBs.
		*	AWS claims it to be 5x greater performance than MySQL on RDS & 3x greater performance than PostgreSQL on RDS.
		*	Storage grows automatically in the lotsize of 10GB upto 64TB.
		*	Can have 15 replicas compared to other DBs i.e. 5 replicas & the replication process is faster.
		*	Failover is instantaneous with sub 10ms replica lag.
		*	Higher availability due to cloud native DB.
		*	20% more expensive with greater efficiency.
		*	**High Availability & Read Scaling:** 
			*	6 copies of data across 3 AZs.
				*	4/6 copies are for write.
				*	3/6 copies are for reads.
			*	Self-healing with peer-to-peer replication.
			*	Storage is stripped among 100s of volumes.
			*	Can have Master/Primary DB+15 read replicas. Any of the replica can be converted to the Master/Primary for failover.
			*	Automated failover for Master/Primary DB avg. time 30 secs.
			*	Supports cross-region replication.
		*	**Aurora DB Cluster:** 
			*	**Writer Endpoint:** DNS pointing to Master/Primary DB regardless of failovers.
			*	**Reader Endpoint:** DNS pointing to the loadbalancer of read replicas.
		*	**Aurora Security:** Same as other RDS security.
		*	**Aurora Serverless:** 
			*	Auto-scaling based on actual usage.
			*	Good for unpredictable workloads.
			*	No capacity planning needed.
			*	Pay-per-second billing.
		*	**Aurora Multi-Master:**
			*	For immediate failovers for R/W nodes.
			*	Every node does R/W.
		*	**Global Aurora:** Cross-region DB.
			*	Cross-region read replicas.
			*	1 Primary R/W region, upto 5 R/O regions, replication lag < 1 second.
			*	Upto 16 read replicas per region.
## ElastiCache
*	**Elasticache:** Managed cache service.
	*	**Service:** Regional
	*	Supports Redis & Memcached.
	*	Involves heavy application side changes.
	*	OS Patching, monitoring, failure recovery, backups, setup, configuration is done by AWS.
	*	**Redis v/s Memcached:**
		*	Multi-AZ with failover | Multi-node for partitioning of data (sharding).
		*	Read replicas for scaling for high availability | No replication i.e. no high availability.
		*	Data durability using AOF persistance. | N/A
		*	Backup & restore | No backup & restore.
		*	N/A | Multi-threaded architecture.
	*	Caches do not support IAM authentication, only Elasticache does with API level security.
	*	Redis AUTH is supported.
	*	Memcached supports SASL authentication.
	*	**ElastiCache Patterns:** 
		*	**Lazy Loading:** Only requested data is cached.
			*	***Pros:*** 
				*	Leads to saving of the memory compromising other unconditional data.
			*	***Cons:*** 
				*	Cache miss results in 3 trips resulting in a noticable delay.
				*	Stale data and due to this the old data in the cache has no updates.
		*	**Write-through:** Adds/Updates data in the cache when updated in the DB.
			*	***Pros:***
				*	Data is never stale.
				*	Every write involves 2 trips.
			*	***Cons:***
				*	Missing data due to the creation of new node, until added/updated again.
				*	**Cache churn:** Most of the data is never read leading to wastage of resources.
		*	**Adding TTL:** 
			*	**TTL aka. Time To Live:** Integer value specifying number of seconds until the key expires.
	*	**Use case:** Making real-time gaming leaderboards using Redis sorted sets, sorting the newly added/updated data in the real-time.
## Route 53
*	**Route 53:** Managed DNS service.
	*	**Service:** Global
	*	**Some important records:** 
		*	**A**: Maps hostname to IPv4. Eg: *example.com* linked to IP *93.184.216.34*.
		*	**AAAA**: Maps hostname to IPv6. Eg: *example.com* linked to IP *2606:2800:220:1:248:1893:25c8:1946*.
		*	**CNAME:** Maps subdomain to another hostname or subdomain. Eg: *docs.example.com* pointing to *apps.com*.
		*	**ALIAS:** Maps hostname to AWS resource.
	*	**TTL:** *Time to Live* of the DNS request in the browser's cache.
		*	**High TTL (eg: 24hrs):**
			*	Less traffic on DNS server.
			*	Greater possibility of DNS records being outdated.
		*	**Low TTL (eg:60secs):**
			*	More traffic on DNS server.
			*	Less chances of records being outdated.
		*	TTL is mandatory.
		