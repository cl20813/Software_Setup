
# VPN

# Connect cluster
open command prompt and type:   
ssh <jl2815>@amarel.rutgers.edu   

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

Now we need to connect compute node. The simplest way:   
srun --time==10:00 --pty bash           (jl2815@slepner2815, this will be the compute node)   
module list   
R  (run R)   
quit()   
exit()   exit compute note        

http://ondemand.hpc.rutgers.edu      (rutgers vpn should be connected) This will give you graphical interface   
login     
interactive apps - amarel desktop - launch novp?   
or you can use jupyer notebook in interactive apps   

http://ondemand.hpc.rutgers.edu:3443   
This is a fast x a littel different environment more suitable for R. Unlike above, this is not connected to compute note automatically, so you have to connect a compute note again.   
srun --time==10:00 --pty bash   







