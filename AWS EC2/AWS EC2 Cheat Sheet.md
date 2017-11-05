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
Enhanced Networking | 
 || -Get higher PPS (packet per second)				
 | -Lower jitter & latency				
 | -Must install driver and supported AMI				
 | -Not available on all instance types				
EBS Optimized | Dedicated throughput/bandwidth from 425 Mbps to 14 000 Mbps.			
 | -Minimize contention between EBS I/O and other traffic from the instance.				
Default | 20 instances per account.		

Instance | AMIs			  
---------|-----------
AWS | Linux, Redhat, Suse Ubuntu & Windows			  	
Market Place | Purchasable AMIs			     	
Custom | Your own AMIs			  	
Community | Shared and free AMIs			
Other supported OS | Fedora, Debian, CentOS, Gentoo Linux, Oracle Linux & FreeBSD			


			
Security Groups	| 
--------------- | 	
 | -Virtual firewall that controls traffic.				
 | -ALLOW traffic only, the rest is DENIED.				
 | -Associated with a Network Interface.				
 | -Stateful outbound and INBOUND.			
 | -Default for custom SG is to ALLOW all outbound and DENY all inbound.				
 | -500 SG per VPC (per region)		
 | -50 Rules per SG		
 | -5 SG per Network Interface		

Has its own Cheat Sheet |
------------------------ |
 | Auto Scaling  
 | Elastic Load Balancing  
			