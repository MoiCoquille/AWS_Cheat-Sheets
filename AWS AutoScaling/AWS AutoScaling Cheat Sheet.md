**AWS EC2 Cheat Sheet**  
by Veronique Robitaille (v@indalit.com) 
  
**!!! Download PDF for single page formatting !!!** 


Types of Instances  | Details |
------------------- | ----------------
General Purpose | T2, M3, M4    |
Compute Optimized | C3, C4 |
Memory Optimized | X1, R3, R4 |   
Accelerated Computing | P2, P3, G3, F1 |      
Storage Optimized | I3, D2      |





What is Auto Scaling?	|
---------------------- |
A method by which you can have instan-	
ces added/removed on the fly.	|
	
Configuration Elements of Auto Scaling	|
--------------------------------------- | -------------------
Minimum Size	| Minimum number of instances that should always be running.	|
Maximum Size	| Maximum number of running instances.	|
Desired Capacity	| Number of instances that should be running when there are no scaling activites.	|
	
Characteristics of Auto Scaling	
Lifecycle Hooks	
  -  They perform custom actions at launch	
     and termination of an instance.	
Termination Protection	
  -  Instances can be protected from a	
    scale-in activity to keep them running.	
Automatic Balancing of instances	
  -  If you have more than one AZ then Auto	
     Scaling will automatically balance them.	
	
Monitoring	
1) Health checks that verify the status of 	
the instances.  This is done by EC2 status 	
checks, ELB & custom health checks.	
2) CloudWatch Metrics to monitor the ins-	
tances and tell Auto Scaling when an ins-	
tance is unhealthy.	
3) CloudWatch Events which monitors	
specific events like launching or termina-	
ting an instance and when Lifecycle  	
Actions occur.	
	
Limits	
Launch Configurations per region         100	
Auto Scaling Groups per region              20	
Scaling Policies per group                        50	
Scheduled Actions per group                125	
Lifecycle Hooks per group                       50	
Step Adjustments per Scaling Policy      20	
Launch Configuration per group            1	