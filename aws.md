The following internet gateway are attached to VPC and cannot be deleted.

This DHCP option set is in use and cannot be deleted. You can't delete a DHCP option set that is associated with a VPC. Associate a different DHCP option set with your VPCs.

VPC 를 삭제해야함
VPC dashboard- Your VPCs-action- delete vpc

여기서 일부 안되는 것
1. The VPC contains one or more in-use network interfaces 
2. The VPC contains one or more NAT gateways

여기에 network interfaces 가서 지우려고 하니
The VPC contains one or more NAT gateways
그래서 2.와 관련하여 NAT gateways를 먼저 delete 해야한다. 그리하면 자동으로 network interfaces 도 삭제된다. 

그 다음에 VPC 삭제 가능
혹시나 하는 차원에서 VPC dashboard 에서 열린 것 모두 삭제

그 다음에 Elastic IP를 release 해야 they are no longer associated with my account

VPC (Virtual Private Cloud) is a virtual network dedicated to your AWS account. It allows you to launch AWS resources. (My own isolated network within cloud it uses private IP)

NAT Gateway (Network Address Translation 네트워크 주소 변환 ex)IPv4): To connect my instances in the VPC to the internet, translate my IP address of my instances to a public IP address. This allows outbound traffic from your instances to reach the internet but prevents unsolicited inbound traffic reaching your instances, so connect to internet while remaining private. 

Network Interface, virtual interface, is the point of interconnection between my instances and a network. 

VPC keeps my resources isolated, NAT Gateway lets them reach internet, and the network interface connects your instances to the network. 

Instances are like virtual machines(or virtual server), run operating systems and applications just like physical computers.

CREATE VPC (isolated network with private IP) Launch Instances within this VPC - Configure Network Interface(ensure each instance has a network interface connected to the VPC) - SET UP NAT Gateway (enables instances with private IP to reach internet with public IP) - Route Traffic: Configure the route tables to direct internet bound traffic. 

SERVER: is a computer that provides data, services, or programs to other computers

-Create VPC: Define IP address range for the VPC. VPC has diablo characters(instances) with private IPs.
-Create subnets for instances connect via NAT gateway. So each instance(character) has its uniqe network configuration within VPC. 
-Use private IP addresss for interval communication between instances. For public communication, (game login) map to public IP via NAT.
