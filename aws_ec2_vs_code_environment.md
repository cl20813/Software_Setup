
## Launch Instance

Name and tags: ```gems_tco```   
```Amazon Linux 2023 AMI Kernel 6.1```   
```64-bit(x86)``` (arcithecture that is optimized for cpu process)   
Instance type: ```c6i.2xlarge```   
key_pair (login) ```gems_tco_key``` saved in download directory.
Security: ```Allow ssh traffic from my IP: 128.6.147.81/32```  81/32 use either one, and if my mac IP changes, then

Inbound rules - Edit inbound rules - ```type:ssh, source:custom, 128.6.147.81/32``` and then click save rules.

## Connect VS-Code
### Elastic IP
Go to  Elastic IPs in EC2 and then allocate default - action - associate instance.

### VS code
On the left, click remote explorer - enter ```ssh ec2-user@128.6.147.81``` then open configuration file and type:

Host AWS_EC2
     HostName 52.21.144.182 (elastic IP)
     User ec2-user (default)
     IdentifyFile /Users/joonwonlee/Documents/AWS/gems_tco_key.pem (I generated and saved the key file when lanuching the instance above -key_pair   

     
