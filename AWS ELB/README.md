AWS ELB (Elastic Load Balancing) Cheat Sheet								
by Veronique Robitaille (v@indalit.com)		



 Something here | Description | Application | Network | Classic |
--------- | ----------- | ------------- | ---------- | ---------
Protocols |	Layer 4 and layer 7 load balancing. Internet or internal facing ELB. | HTTP/HTTPS |	TCP	| TCP/SSL HTTP/HTTPS |
Health Checks |	ELB monitors and sends traffic only to healthy targets or instances. | HTTP/HTTPS |	TCP HTTP/HTTPS | TCP/SSL HTTP/HTTPS
Round Robin	|	Routing Algorithm, even distribution.	|	√	|		|	√
Least Outstanding		Routing Algorithm, least connections.						√
Flow Hash	|	Routing Algorithm, a hash of packet elements.	|		|	√	|	
Configuration Specifications		Must be in one VPC.  Can be in many AZs.  Must be in a one subnet per AZ.		√				√
Zonal isolation	|	Distributes traffic evenly in a single AZ.  Can fail over to other AZ or region if all targets in initial AZ are unhealthy.	|		|	√	|	
Auto Scaling		Automatically register and deregister instances with ELB.		√		√		√
Sticky Sessions	|	Mechanism to route requests from the same client to the same target or instance.	|	√	|		|	√
Path/Host based routing		foo.com/images and images.foo.com		√				
Multiple port routing	|	Route to many ports on single target.	|	√	|	√	|	
HTTP/2		Support for HTTP/2		√				
Websockets 	|	Provides bi-directional communication channels between a client and a server over a long-running TCP connection.	|	√	|	√	|	
SSL Offloading		ELB encrypts and decrypts HTTPS requests.		√				√
Multiple SSL Certificates	|	Can have more than one SSL certificate on ELB.	|	√	|		|	
SNI		ELB can present many certificates which enable it to support many websites using a single secure listener.		√				
Pricing	|		|	per hour   per LCU	|	per hour   per LCU	|	per hour   per GB
ELB per region				20		20		20
Subnets per AZ per ELB	|		|	1	|	1	|	1
IPv6 support				√				
AWS ECS support	|	Container-based applications.	|	√	|	√	|	
X-Forward-For		Header to send info about the HTTP message.		√				√
Proxy header	|	Provides client information.	|		|		|	TCP/SSL
Preserve source IP		Preserves client side source IP allowing the back-end to see it. 				√		
Connection Draining	|	Time to complete existing connections when target/instance is unhealthy.	|	√	|	√	|	√
IP as a target		An IP can be used as a target instead of an instance.  Works for on-premises resources.		√		√		
Logging	|	Access logs written to S3 or CloudWatch.	|	√	|	√	|	√
Request Tracing		Allow each request to be uniquely identified, providing improved monitoring and request-level diagnostics.		√				
AWS WAF	|	Works with a web application firewall that protects from malicious requests.	|	√	|		|	
Cross-zone load balancing		Distributes traffic evenly across all AZs		√				√
Static IP	|	Provides a static IP for the lELB.	|		|	√	|	
EIP		Assign EIP to the ELB.				√		