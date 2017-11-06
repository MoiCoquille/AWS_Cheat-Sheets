**AWS EC2 Cheat Sheet**  
by Veronique Robitaille (v@indalit.com) 
  
**Download PDF for single page formatting** 

<table>
<tr><th>Table 1 Heading 1 </th><th>Table 1 Heading 2</th></tr>
<tr><td>

Types of Instances	|	Details |
------------------- | ----------------
General Purpose	| T2, M3, M4		|
Compute Optimized	| C3, C4 |
Memory Optimized | X1, R3, R4 |		
Accelerated Computing	| P2, P3, G3, F1 |			
Storage Optimized	| I3, D2			|

</td><td>

Instances Main Characteristics | Details |
------------------------------ | ------------------------				
vCPU | Virtual CPU			|
Memory	| GiB		  
Storage | Instance store, EBS SSD & HDD		|		 
Enhanced Networking |  |
 || -Get higher PPS (packet per second)			|	
 || -Lower jitter & latency				|
 || -Must install driver and supported AMI	|			
 || -Not available on all instance types				|
EBS Optimized | |
 || -Dedicated throughput/bandwidth from 425 Mbps to 14 000 Mbps.		|	
 || -Minimize contention between EBS I/O and other traffic from the instance.		|		
Default | 20 instances per account.		|

</td></tr> </table>


<table>
<tr><th>Table 1 Heading 1 </th><th>Table 1 Heading 2</th></tr>
<tr><td>

|Table 1| Middle | Table 2|
|--|--|--|
|a| not b|and c |

</td><td>

|b|1|2|3| 
|--|--|--|--|
|a|s|d|f|

</td></tr> </table>


Instance | AMIs			  
---------|-----------
AWS | Linux, Redhat, Suse Ubuntu & Windows			  	
Market Place | Purchasable AMIs			     	
Custom | Your own AMIs			  	
Community | Shared and free AMIs			
Other supported OS | Fedora, Debian, CentOS, Gentoo Linux, Oracle Linux & FreeBSD			


			
Security Groups	| 
--------------- | 	
 | Virtual firewall that controls traffic.				
 | ALLOW rules only			
 | Associated with a Network Interface.				
 | Stateful outbound and INBOUND.			
 | Default for custom SG is to ALLOW all outbound and DENY all inbound.				
 | 500 SG per VPC (per region)		
 | 50 Rules per SG		
 | 5 SG per Network Interface		



Instances Pricing Model |  Details
------------------------ | ------------------ 
On-demand | Pay per second when instance is running
   || No contract
Reserved | No, partial or full upfront
   || Can be applied to an AZ or a region, capacity reservation only if applied to AZ.
   || Modyfing, exchanging an instance is only available on certain OS.
  -1-  Standard | 1 or 3 year contract
   || Can exchange within same instance family using a normalisation factor.
  -2-  Convertible |  3 year contract only
   || Can change instance family.
   || Can only be exchanged to same or higher payment option.
   || Can exchange for 1 or many instances as long as the price is equal or higher.
SPOT | Bid on spare capacity at Market Price.
Dedicated Instance | Hourly usage fee + per region fee
   || Dedicated physical server/host
   || Per instance billing
   || You can have dedicated SPOT instances.
Dedicated Host | Per host billing
   || Visibility of the number of sockets and physical cores.  
   || Visibility and control over how instances are placed.  
   || Ideal for server-bound software and compliance & regulatory requirements. 
   || Per family type  
Scheduled | Pay for scheduled slots
   || 1 year contract



  
Other       | Details
----------- | -------------
EIP | Static IPv4 address (5 per region)
   || Associated to a Network Interface
   || Hourly charge if not used or more than one per instance.
   || Can remap from one instance to another.
ENI | Default is the Primary Network Interface (eth0) and cannot be detached.
   || Can attach/detach other ENI from one instance to another.
   || Limit varies on instance type.



  
Placement Group |  
----------------|
| Logical grouping of instances in a single AZ for better network performance.  
| Better to launch all instances at once and use the same type. 



Has its own Cheat Sheet |
------------------------ |
 | Auto Scaling  
 | Elastic Load Balancing  


 Types of Instances | Details |
------------------- | ----------------
General Purpose | T2, M3, M4    |
Compute Optimized | C3, C4 |
Memory Optimized | X1, R3, R4 |   
Accelerated Computing | P2, P3, G3, F1 |      
Storage Optimized | I3, D2      |



Instances Main Characteristics | Details |
------------------------------ | ------------------------       
vCPU | Virtual CPU      |
Memory  | GiB     
Storage | Instance store, EBS SSD & HDD   |    
Enhanced Networking |  |
 || -Get higher PPS (packet per second)     | 
 || -Lower jitter & latency       |
 || -Must install driver and supported AMI  |     
 || -Not available on all instance types        |
EBS Optimized | |
 || -Dedicated throughput/bandwidth from 425 Mbps to 14 000 Mbps.   | 
 || -Minimize contention between EBS I/O and other traffic from the instance.   |   
Default | 20 instances per account.   |
			