**AWS EC2 Cheat Sheet**  
by Veronique Robitaille (v@indalit.com)  


Types of Instances	|	Details
------------------- | ----------------
General Purpose	| T2, M3, M4		
Compute Optimized	| C3, C4
Memory Optimized | X1, R3, R4		
Accelerated Computing	| P2, P3, G3, F1			
Storage Optimized	| I3, D2			



Instances Main Characteristics | Details
------------------------------ | ------------------------				
vCPU | Virtual CPU			
Memory	| GiB		  
Storage | Instance store, EBS SSD & HDD				 
Enhanced Networking | Get higher PPS (packet per second)				
 | Lower jitter & latency				
  | Must install driver and supported AMI				
   | Not available on all instance types				
EBS Optimized | Dedicated throughput/bandwidth from 425 Mbps to 14 000 Mbps.			
    | Minimize contention between EBS I/O and other traffic from the instance.				
Default | 20 instances per account.		



			Dedicated Host	Per host billing
Instance AMIs			  -  Visibility of the number of sockets and physical cores.	
AWS: Linux, Redhat, Suse Ubuntu & 			  -  Visibility and control over how instances are placed.	
Microsoft			  -  Ideal for server-bound software and compliance & 	
Market Place: Purchasable AMIs			     regulatory requirements.	
Custom: Your own AMIs			  -  Per family type	
Community: Shared and free AMIs			Scheduled	Pay for scheduled slots
Other supported OS: Fedora, Debian, 			 	1 year contract
CentOS, Gentoo Linux, Oracle Linux & 				
FreeBSD			Other	
			EIP	Static IPv4 address (5 per region)
Security Groups				Associated to a Network Interface
Virtual firewall that controls traffic.				Hourly charge if not used or more than
ALLOW traffic only, the rest is DENIED.				one per instance.
Associated with a Network Interface.				Can remap from one instance to another.
Stateful outbound and INBOUND.			ENI	Default is the Primary Network Interface
Default for custom SG is to ALLOW all out-				(eth0) and cannot be detached.
bound and DENY all inbound.				Can attach/detach other ENI from one
SG per VPC (per region)	500			instance to another.
Rules per SG	50			Limit varies on instance type.
SG per Network Interface	5			
			Placement Group	
Has it's own Cheat Sheet			Logical grouping of instances in a single AZ for better network	
Auto Scaling			performance.	
Elastic Load Balancing			Better to launch all instances at once and use the same type.	