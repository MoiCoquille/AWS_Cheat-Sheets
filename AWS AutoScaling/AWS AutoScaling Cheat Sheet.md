# AWS Auto Scaling Cheat Sheet 
by Veronique Robitaille (v@indalit.com) 
<br />

### Check out PDF version 

<br />


<table>
	<tr>
		<td align="center" colspan="2"><b>What is Auto Scaling?</b></td>
	</tr>
	<tr>
		<td colspan="2">A method by which you can have instances added/removed on the fly.</td>
	</tr>
</table>

	<tr>
		<td align="center" colspan="2"><b>Configuration Elements of Auto Scaling</b></td>
	</tr>
	<tr>
		<td>Minimum Size</td>
		<td>Minimum number of instances that should always be running.</td>
	</tr>
	<tr>
		<td>Maximum Size</td>
		<td>Maximum number of running instances.</td>
	</tr>
	<tr>
		<td>Desired Capacity</td>
		<td>Number of instances that should be running when there are no scaling activites.</td>
	</tr>

	<tr>
		<td align="center" colspan="2"><b>Characteristics of Auto Scaling</b></td>
	</tr>
	<tr>
		<td>Lifecycle Hooks</td>
		<td>They perform custom actions at launch and termination of an instance.</td>
	</tr>
	<tr>
		<td>Termination Protection</td>
		<td>Instances can be protected from a scale-in activity to keep them running.</td>
	</tr>
	<tr>
		<td>Automatic Balancing of instances</td>
		<td>If you have more than one AZ then Auto Scaling will automatically balance them.</td>
	</tr>

	<tr>
		<td align="center" colspan="2"><b>Monitoring</b></td>
	</tr>
	<tr>
		<td colspan="2">Health checks that verify the status of the instances.  This is done by EC2 status checks, ELB & custom health checks.</td>
	</tr>
	<tr>
		<td colspan="2">CloudWatch Metrics to monitor the instances and tell Auto Scaling when an instance is unhealthy.</td>
	</tr>
	<tr>
		<td colspan="2">CloudWatch Events which monitors specific events like launching or terminating an instance and when Lifecycle Actions occur.</td>
	</tr>

	<tr>
		<td align="center"><b>Limits</b></td>
		<td align="center"><b>Number</b></td>
	</tr>
	<tr>
		<td>Launch Configurations per region</td>
		<td align="center">100</td>
	</tr>
	<tr>
		<td>Auto Scaling Groups per region</td>
		<td align="center">20</td>
	</tr>
	<tr>
		<td>Scaling Policies per group</td>
		<td align="center">50</td>
	</tr>
	<tr>
		<td>Scheduled Actions per group</td>
		<td align="center">125</td>
	</tr>
	<tr>
		<td>Lifecycle Hooks per group</td>
		<td align="center">50</td>
	</tr>
	<tr>
		<td>Step Adjustments per Scaling Policy</td>
		<td align="center">20</td>
	</tr>
	<tr>
		<td>Launch Configuration per group</td>
		<td align="center">1</td>
	</tr>

	<tr>
		<td align="center" colspan="2"><b>Types of Auto Scaling</b></td>
	</tr>
	<tr>
		<td>Fleet Management</td>
		<td>Keeps a fixed number of instances running.  Does not react to spikes in traffic.</td>
	</tr>
	<tr>
		<td>Manual Scaling</td>
		<td>Change manually the number of desired instances.</td>
	</tr>
	<tr>
		<td>Schedule Scaling</td>
		<td>Scaling-in and scaling-out is configured at specific times and dates.</td>
	</tr>
	<tr>
		<td>Dynamic Scaling</td>
		<td>Scaling-in and scaling-out happens based on configured rules called policies.</td>
	</tr>
	<tr>
		<td>(1) Simple Scaling Policy </td>
		<td>Uses a metric like CPU utlisation to scale.</td>
	</tr>
	<tr>
		<td>(2) Step Scaling Policy</td>
		<td>Like Simple Scaling but has multiple stepsto scale.  These steps are called Step Adjustments.</td>
	</tr>
	<tr>
		<td>(3) Target Tracking Scaling Policy</td>
		<td>Keeps instance at a fixed level using, for example, CPU utilization.</td>
	</tr>

	<tr>
		<td align="center" colspan="2"><b>Components of Auto Scaling</b></td>
	</tr>
	<tr>
		<td>Launch Configuration</td>
		<td>Template used to launch a new instance.  Is composed of the instance type, OS, userdata...  Cannot make modifications to one.</td>
	</tr>
	<tr>
		<td>Auto Scaling Group </td>
		<td>Group of instances that share a Launch.  Configuration and scale based on policies.</td>
	</tr>
	<tr>
		<td>Scaling Policy</td>
		<td>Rule or rules that start a scaling activity (adding or removing instances from an auto Scaling Group).  Can have more than one policy per Auto Scaling Group.</td>
	</tr>
	<tr>
		<td colspan="2">When more than one Scaling Policy for an Auto Scaling Group, Auto Scaling will choose a policy with the highest impact on the number of instances.</td>
	</tr>

	<tr>
		<td align="center" colspan="2"><b>Custom Termination Policy </b></td>
	</tr>
	<tr>
		<td colspan="2">First, it will make sure instances are balanced between AZs.  If not, then it will choose the AZ with the most instances.</td>
	</tr>
	<tr>
		<td colspan="2">Then choose from the following: OldestInstance, NewestInstance, OldestLaunchConfiguration, Default AWS Termination Policy</td>
	</tr>

	<tr>
		<td align="center" colspan="2"><b>Pricing </b></td>
	</tr>
	<tr>
		<td colspan="2">This service is part of EC2 and is provided for free.  You pay for the instances you use.</td>
	</tr>

</table>	