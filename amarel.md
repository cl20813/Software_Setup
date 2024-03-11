
### Rutgers VPN

Connect cluster 1) commend line access using ssh, 2) Open OnDemand 3) FastX.

## 1) commend line access using ssh

### Connect login node   
open command prompt and type:   
ssh <net_id>@amarel.rutgers.edu   



## Experiments
1.pwd (current working directory)   
2.date (search from paths from 4)      
3.hostname       
4.echo $PATH       
5.module avail      
6.modue use /projects/community/modulefiles/      (this allows you to use softwares not installed in your local computer)   
7.module avail   
8.module spider   
9.module avail R        (R/4.1.0-gc563)   
10.module load R/4.1.0-gc563   
11.which R   
12.ls (list of directory)         

### Connect compute node   
 
The simplest way:      
srun --time==10:00 --pty bash           (jl2815@slepner2815, this will be the compute node)   
module list   
R  (run R)   
quit()   
exit()   exit compute note        

## 2) Open OnDemand interface (graphical desktop environment)

### Rutgers vpn should be connected 
-[Download](https://vpn1.rutgers.edu/+CSCOE+/logon.html#form_title_text)  
- activate vpn   
- start any connect
- download for windows (cisco) and open cisco
- enter "vpn.rutgers.edu" to connect: username: netid, password, 2nd password: 6 digit duo


http://ondemand.hpc.rutgers.edu     
login     
interactive apps - amarel desktop - launch novp?   
or you can use jupyer notebook in interactive apps   

## 3) FastX interface

http://ondemand.hpc.rutgers.edu:3443   
This is a fast x a littel different environment more suitable for R. Unlike Open OnDemandabove, this is not connected to compute note automatically, so you have to connect a compute note again.   
srun --time==10:00 --pty bash   

# Python
Using 2) Open OnDemand, open personal Jupyter. But you need to install your environment in your local jupyter.

-[see here ](install_python.md)









