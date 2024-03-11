
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
6.module use /projects/community/modulefiles/      (this allows you to use softwares not installed in your local computer)   
7.module avail   
8.module spider   
9.module avail R        (R/4.1.0-gc563)   
10.module load R/4.1.0-gc563   
11.which R   
12.ls (list of directory)         

### Connect compute node   
 
The simplest way:      
srun --time=10:00 --pty bash           (jl2815@slepner2815, this will be the compute node)   
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
srun --time=10:00 --pty bash   

# Conda commands
conda remove --name jl2815     
conda env remove --name your_environment_name
conda activate jl2815      
conda deactivate jl2815       
conda list  (check installed packages)   
conda info --root   
conda which    (similar to above)   

# Python

1. commend line access using ssh
Open command prompt and enter "ssh jl2815@amarel.rutgers.edu" and enter the same password for net_id in Rutgers   
2. module use /projects/community/modulefiles  (check if anaconda is available "module avail")   
3. module load anaconda/2023.10-bd387
4. conda init bash   ##configure your bash shell for conda, auto update your .bashrc file
5. cd  (change directory to home directory)
6. source .bashrc
7. mkdir -p .conda/pkgs/cache .conda/envs   ##These are the folders to store your own env you going to build

conda env list

8. conda create --name spa_tmp_pr1  tensorflow==2.3 python=3.8      (/home/<netID>/.conda/envs/tf2)
9. conda activate spa_tmp_pr1


conda install numpy pandas matplotlib seaborn scikit-learn    
conda install xarray jupyter netCDF4
#xarray for netCDF4 and dont forget to install jupyter, otherwise you can't open personal jupyter in amarel.

after seeing `UserWarning: Pandas requires version '1.3.6' or newer of 'bottleneck' (version '1.3.5' currently installed)'     
conda install -c conda-forge --update-deps bottleneck or just !pip install bottleneck in notebook.

12. which conda   this will give you the path (/projects/community/anaconda/2023.10/bd387/base/condabin/conda)
13. Important!
conda install -c anaconda ipykernel (this should be done in an active environment)    
ipython kernel install --user --name=spa_tmp_pr1
11. conda deactivate   
15. Open Ondemand and click personal jupyter. Then open Jupyter 3.

### Now I want to use the same environment in my local computer.

1. conda env export > spa_tmp_pr1.yml    (in my login node prompt)
2. send the yml file to my local computer and copy the path of it. 
3. Open the anaconda powershell prompt and enter   
conda env create --file /Users/joonw/Downloads/spa_tmp_pr1.yml   ("C:\Users\joonw\Downloads\spa_tmp_pr1.yml"

(why error?)   
 










