## Display conda list
```conda info --envs```
```conda env list```

## Remove previous environment
```conda deactivate```
```conda env remove -n gems_tco```



## Create my environment in Python packages

1. ```ssh jl2815@amarel.rutgers.edu```               # Access the command line using SSH
2. ```module use /projects/community/modulefiles```  # Use the community module files
3. ```module avail```                                # Check available Anaconda versions
4. ```module load anaconda/2024.06-ts840```          # Load the desired Anaconda module
5. ```conda init bash```                             # Initialize Conda for Bash
                                                 configure your bash shell for conda(adds necessary Conda initialization code to your .bashrc.), auto update your .bashrc file
                                                 This configuration ensures that the conda command and Conda environments are available every time you opne a new terminal session in the bash shell.
7. ```cd```
8. ```source ~/.bashrc```                            # Source the .bashrc file: This command reloads the .bashrc file, applying the changes made by conda init bash.
9. ```mkdir -p .conda/pkgs/cache .conda/envs```      # It's a preparatory step to ensure you have a dedicated space for your environments and packages.
                                                 .conda/pkgs/cache: This directory can be used to store cached packages.
                                                 .conda/envs: This directory is where you can store your Conda environments.
10. ```conda create --prefix /home/jl2815/.conda/envs/gems_tco python=3.8```
                                               # Create the gems_tco environment within the .conda/envs directory. This keeps your environments organized and separate from the default Conda
'''conda update conda'''                            # (I DON'T HAVE PERMISSION TO WRITE). Upgrade the latest version of conda from *base environment         # check conda --version

11. ```module avail cuda```                          # You need to load the CUDA module before installing Pytorch with CUDA support. 
    ```module load cuda/12.1.0```

12. ```conda activate gems_tco```

13-1 Install Pytorch, torchvision, torchaudio, and CUDA:
```conda install pytorch torchvision torchaudio pytorch-cuda=12.1.0 -c pytorch -c nvidia```   # numpy is installed automatically
13-2 Install TensorFlow:
```conda install tensorflow```
13-3 Install additional Python packages:
```conda install pandas matplotlib seaborn scikit-learn```
```conda install xarray jupyter netCDF4 typing scipy```           # collections and math are part of python standard library.
                                                                   xarray is for netCDF4 and dont forget to install jupyter, otherwise you can't open personal jupyter in amarel.
13-4 Install third-party packages using pip                      # You may not be able to install some of the packages using conda install. Then use pip. Not all packages are included in Conda's repositories.
```pip install scikit-gstat```                                  #import skgstat  !pip in a jupyter notebook
```pip list | grep scikit-gstat```
13-5 Install my package 'gems_tco'
```pip install -e /home/jl2815/tco/```
13-6 Verify installation
```pip list | grep GEMS_TCO```           
```python -c "import GEMS_TCO; print('GEMS_TCO imported successfully')"``` 
```pip show GEMS_TCO```

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
 










