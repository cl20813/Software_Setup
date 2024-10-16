


# Create my environment in Python packages

1. commend line access using ssh
Open command prompt and enter "ssh jl2815@amarel.rutgers.edu" and enter the same password for net_id in Rutgers   
2. module use /projects/community/modulefiles 
3. module avail         (this will show you available versions for anaconda)
4. module load anaconda/2024.06-ts840
5. conda init bash   ##configure your bash shell for conda, auto update your .bashrc file

''' You may skip this part.                 
 conda init bash adds necessary configuration code to your .bashrc. This configuration ensures that the conda command and Conda environments are available every time you opne a new terminal session in the bash shell.            
 Bash shell is a command-line interpret or shell used in many Unix-like operating systems. It allows useres to interact with the operating system by typing commands.                    
 Command Prompt in Windows is command-line interface(CLI) for Windows, bash is primarily used in Unix-like systems such as Linux and macOS.                          
'''                    
                 
6. cd  (change directory to home directory)     
7. source .bashrc  # this command is used to reload the .bashrc file      
8. mkdir -p .conda/pkgs/cache .conda/envs   ## This is the folder to store your own enviornment you going to build.    

conda env list    (View if there are any other environments already exist)       

8. conda create --name gems_tco  tensorflow==2.3 python=3.8      (/home/<netID>/.conda/envs/tf2)
9. conda activate gems_tco
conda install conda=24.9.1        # upgrade the latest version of conda. 
conda install numpy pandas matplotlib seaborn scikit-learn    
conda install xarray jupyter netCDF4 collections  typing scipy math   # collections and math are part of python standard library, so you don't need to instaall them, and skgstat might be third party, I have to use pip
#xarray for netCDF4 and dont forget to install jupyter, otherwise you can't open personal jupyter in amarel.

# You may not be able to install some of the packages using conda install. Then use pip.
pip install <package name>



----------------------------------------------------------------------------------------------------------------------
You can also use OnDemand interface or FastX interface to use amarel.
     
## Open OnDemand interface (graphical desktop environment)

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

## FastX interface (for R studio) You can use gpu for this

[http://ondemand.hpc.rutgers.edu:3443](https://amarel.hpc.rutgers.edu:3443/)   
This is a fast x a littel different environment more suitable for R. Unlike Open OnDemandabove, this is not connected to compute note automatically, so you have to connect a compute note again.   
  
srun --cpus-per-task=2 --time=00:45:00 --pty bash  (2 node)   
module load singularity/3.8.5 (may need to check module --show-hidden avail to find the latest version)
module use /projects/community/modulefiles/   
singularity run --app rstudio /projects/community/singularity.images/rstudio/r402rstudio11.sif-gc563     (run(space)-app(space)   

# other Conda commands
conda remove --name jl2815     
conda env remove --name your_environment_name
conda activate jl2815      
conda deactivate jl2815       
conda list  (check installed packages)   
conda info --root   
conda which    (similar to above)   

## Other exercises
1.pwd (current working directory)   
2.date (search from paths from 4)      
3.hostname       
4.echo $PATH       
8.module spider    # more detail
9.module avail R        (R/4.1.0-gc563)   
10.module load R/4.1.0-gc563               module load R/4.1.0-gc563
11.which R   
12.ls (list of directory)       
13. module purge   : To clear-out your added modules:

### Connect compute node   
 
The simplest way:      
srun --time=10:00 --pty bash           (jl2815@slepner2815, this will be the compute node)   
module list   
R  (run R)   
quit()   
exit()   exit compute note  






after seeing `UserWarning: Pandas requires version '1.3.6' or newer of 'bottleneck' (version '1.3.5' currently installed)'     
conda install -c conda-forge --update-deps bottleneck or just !pip install bottleneck in notebook.

conda install -c conda-forge --update-deps bottleneck (this resolved my issue)

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
 










