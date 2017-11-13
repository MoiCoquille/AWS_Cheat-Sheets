**AWS EC2 Cheat Sheet**  
by Veronique Robitaille (v@indalit.com) 
  
**!!! Download PDF for single page formatting !!!** 


What is Auto Scaling?	|
---------------------- |
A method by which you can have instances added/removed on the fly.	|
	
Configuration Elements of Auto Scaling	| Details |
--------------------------------------- | ------------------- |
Minimum Size	| Minimum number of instances that should always be running.	|
Maximum Size	| Maximum number of running instances.	|
Desired Capacity	| Number of instances that should be running when there are no scaling activites.	|
	

Characteristics of Auto Scaling	 | Details |
-------------------------------- | -------- |
Lifecycle Hooks	| They perform custom actions at launch	and termination of an instance.	|
Termination Protection	| Instances can be protected from a	scale-in activity to keep them running.	|
Automatic Balancing of instances	| If you have more than one AZ then Auto Scaling will automatically balance them.	|
	
Monitoring	|
----------- |
Health checks that verify the status of the instances.  This is done by EC2 status checks, ELB & custom health checks. |
CloudWatch Metrics to monitor the instances and tell Auto Scaling when an instance is unhealthy.	|
CloudWatch Events which monitors specific events like launching or terminating an instance and when Lifecycle Actions occur. |
	
Limits	| Number |
------- | ------ |
Launch Configurations per region | 100	|
Auto Scaling Groups per region | 20	|
Scaling Policies per group | 50 |	
Scheduled Actions per group | 125 |	
Lifecycle Hooks per group | 50 |	
Step Adjustments per Scaling Policy | 20 |	
Launch Configuration per group | 1 |	