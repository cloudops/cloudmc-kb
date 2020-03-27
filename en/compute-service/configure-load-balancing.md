---
title: "Configure Load Balancing"
slug: configure-load-balancing
---


Load balancing provides a way to distribute workloads across multiple compute resources. This usually increases performance and availability through redundancy. In the context of cloud.ca, this is achieved by associating load-balancing rules to a VPC's public IP address.

Note: you cannot configure load balancing rules on a public IP address already being used for Source NAT, VPN or Port Forwarding. Furthermore, only a single tier within a VPC can have public IP addresses dedicated to load-balancing.

In the following example, we will enable load balancing for HTTP (TCP port 80) on instances web1 and web2 using a simple round-robin scheduling algorithm.

Go to the Services page.
Select the appropriate compute environment on the left sidebar.
Select the Networking tab.
From the target VPC's list item, click the Public IPs button.
Click on Acquire IP address




Add a load balancing rule to the newly acquired Public IP address:




Name your new rule, then specify the TCP port to load-balance and indicate the tier containing the target instances:


Select the desired balancing algorithm. In this case, we don't prescribe any stickiness policy and we load-balance TCP traffic:




Select the instances that you wish to load-balance:


You will then get confirmation that the rules were successfully applied:


Click on the Public IP addresses link in the breadcrumb and validate that the displayed information reflects your newly created rule:


Finally, check the load-balancing rules are working as expected by running some traffic and verify if each server is serving an equal share of the requests. One way you can achieve this is by forcing each server to return a slightly different answer (e.g.: the host name of the server) in its response (or response headers).
