# AWS Storage Gateway Cheat Sheet 
by Veronique Robitaille (v@indalit.com) 
<br />
<br />

<table>
	<tr>
		<td align="center" colspan="2"><b>General Characteristics</b></td>
	</tr>
	<tr>
		<td colspan="2">3 types of gateways available(NFS or iSCSI):</td>
	</tr>
	<tr>
		<td></td>
		<td>- File Gateway</td>
	</tr>
	<tr>
		<td></td>
		<td>- Volume Gateway</td>
	</tr>
	<tr>
		<td></td>
		<td>- Tape Gateway</td>
	</tr>
		<tr>
		<td colspan="2">You install the Gateways with a provided image on a	on-premises server VM.  Also possible on an instance.</td>
	</tr>
	<tr>
		<td colspan="2">VM software is either VMware ESXi or Microsoft Hyper-V.</td>
	</tr>
	<tr>
		<td colspan="2">Objects on S3 are encrypted using S3 SSE-S3 (S3 managed encryption keys).</td>
	</tr>
	<tr>
		<td colspan="2">Data also encrypted on Glacier.</td>
	</tr>
	<tr>
		<td colspan="2">Data transfer from Gateway to S3 and Glacier uses SSL.</td>
	</tr>
	<tr>
		<td align="center" colspan="2">&nbsp;</td>
	</tr>
	<tr>
		<td align="center" colspan="2"><b>Gateway Minimum Hardware Requirements</b></td>
	</tr>
	<tr>
		<td colspan="2">4 virtual processors assigned to the VM</td>
	</tr>
	<tr>
		<td colspan="2">16 GB of RAM assigned to the VM</td>
	</tr>
	<tr>
		<td colspan="2">80 GB of disk space for installation of VM image and system data</td>
	</tr>
	<tr>
		<td colspan="2">If an installation on an instance then use a xlarge type minimum.</td>
	</tr>
	<tr>
		<td colspan="2">Updates and patches automatically deployed during weekly maintenance schedule.  Short downtime.</td>
	</tr>
	<tr>
		<td align="center" colspan="2">&nbsp;</td>
	</tr>
	<tr>
		<td align="center" colspan="2"><b>Pricing of Storage Gateway</b></td>
	</tr>
	<tr>
		<td colspan="2">Storage on S3 (file & volume)</td>
	</tr>
	<tr>
		<td colspan="2">Snapshot storage in EBS</td>
	</tr>
	<tr>
		<td colspan="2">Virtual Tape storage (inlcuding archived)</td>
	</tr>
	<tr>
		<td colspan="2">Data written to AWS storage by the Gateway</td>
	</tr>
	<tr>
		<td colspan="2">Virtual Tape retrieval</td>
	</tr>
	<tr>
		<td colspan="2">Data transfer OUT from AWS Storage Gateway service to EC2 hosted Gateway and on-premises Gateway</td>
	</tr>
	<tr>
		<td align="center" colspan="2">&nbsp;</td>
	</tr>
	<tr>
		<td align="center" colspan="2"><b>File Gateway</b></td>
	</tr>
	<tr>
		<td colspan="2">The protocol to access the File Gateway is NFS 3 or 4.1.</td>
	</tr>
	<tr>
		<td colspan="2">Files are stored as objects on S3.</td>
	</tr>
	<tr>
		<td colspan="2">Local cache for recently accessed data.</td>
	</tr>
	<tr>
		<td colspan="2">On S3, lifecycle policies, cross-region replication and versioning are available features.</td>
	</tr>
	<tr>
		<td colspan="2">Asynchronously updates the objects on S3.</td>
	</tr>
	<tr>
		<td colspan="2">Max 1 file share per S3 bucket, max 10 file shares per Gateway and max size of a file is 5TB.</td>
	</tr>
	<tr>
		<td colspan="2"><b>Optimized data transfer:</b></td>
	</tr>
	<tr>
		<td></td>
		<td>- Uses multipart uploads and copy put, so only changed data is uploaded to S3.</td>
	</tr>
	<tr>
		<td></td>
		<td>- Uses byte-range downloads.</td>
	</tr>
	<tr>
		<td align="center" colspan="2">&nbsp;</td>
	</tr>
	<tr>
		<td align="center" colspan="2"><b>Volume Gateway</b></td>
	</tr>
	<tr>
		<td colspan="2">Mount volumes as iSCSI devices.</td>
	</tr>
	<tr>
		<td colspan="2">Asynchronous incremental backups done via snapshots that are stored as EBS snapshots.</td>
	</tr>
	<tr>
		<td colspan="2">Can restore snapshots less than 16TB to EC2 instances.</td>
	</tr>
	<tr>
		<td colspan="2">Max 32 volumes per Gateway.</td>
	</tr>
	<tr>
		<td colspan="2">When considering local storage size, need to take into account size of file store and upload buffer.</td>
	</tr>
	<tr>
		<td colspan="2"><b>Cached Volumes:</b></td>
	</tr>
	<tr>
		<td></td>
		<td>- Store data on S3</td>
	</tr>
	<tr>
		<td></td>
		<td>- Cache frequently accessed data locally</td>
	</tr>
	<tr>
		<td></td>
		<td>- Max volume size 32TB, max storage 1PB</td>
	</tr>
	<tr>
		<td></td>
		<td>- Allocate minimum 20% of file store size to local cache storage (hard drives)</td>
	</tr>
	<tr>
		<td></td>
		<td>- Data not available via S3</td>
	</tr>
	<tr>
		<td colspan="2"><b>Stored Volumes:</b></td>
	</tr>
	<tr>
		<td></td>
		<td>- Data stored locally (on Gateway)</td>
	</tr>
	<tr>
		<td></td>
		<td>- Asynchronous backup via snapshots to S3</td>
	</tr>
	<tr>
		<td></td>
		<td>- Max volume size 16TB, max storage 512TB</td>
	</tr>
	<tr>
		<td></td>
		<td>- Map storage volumes to on-premises DAS or SAN using iSCSI</td>
	</tr>
	<tr>
		<td align="center" colspan="2">&nbsp;</td>
	</tr>	
	<tr>
		<td align="center" colspan="2"><b>Tape Gateway (VTL Virtural Tape Library)</b></td>
	</tr>
	<tr>
		<td colspan="2">Backup to S3 and archieval solution to Glacier.</td>
	</tr>
	<tr>
		<td colspan="2">Requires a client backup software.</td>
	</tr>
	<tr>
		<td colspan="2">Available as iSCSI devices.</td>
	</tr>
	<tr>
		<td colspan="2">A tape is write protected, it is read-only.</td>
	</tr>
	<tr>
		<td colspan="2">Retrieval from tape takes 3 to 5 hours.</td>
	</tr>
	<tr>
		<td colspan="2">Tape size from 100GB to 2.5TB, max 1500 tapes or max 1PB per VTL.</td>
	</tr>
	<tr>
		<td colspan="2">Virtual Tape Shelf can store unlimited amount of data on Glacier.</td>
	</tr>
	<tr>
		<td colspan="2">Asynchronous backups.</td>
	</tr>
	<tr>
		<td colspan="2"><b>Supported Backup Applications:</b></td>
	</tr>
	<tr>
		<td></td>
		<td>- Arcserve Backup</td>
	</tr>
	<tr>
		<td></td>
		<td>- Commvault</td>
	</tr>
	<tr>
		<td></td>
		<td>- DellNetvault Backup</td>
	</tr>
	<tr>
		<td></td>
		<td>- EMC Networker</td>
	</tr>
	<tr>
		<td></td>
		<td>- HPE Data Protector</td>
	</tr>
	<tr>
		<td></td>
		<td>- Microsoft System Center Data Protection Manager</td>
	</tr>
	<tr>
		<td></td>
		<td>- Veeam Backup and Replication</td>
	</tr>
	<tr>
		<td></td>
		<td>- Veritas Backup Exec</td>
	</tr>
</table>	