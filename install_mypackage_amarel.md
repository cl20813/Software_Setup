## Copy package folder

### Important!
```set_up.py``` should be in the TCO directory at the same level as the package folder GEMS_TCO, while ```init.py``` should be inside the ```GEMS_TCO``` folder."

```scp "C:\Users\joonw\anaconda3\envs\jl2815\Lib\site-packages\GEMS_TCO\setup.py" jl2815@amarel.rutgers.edu:/home/jl2815/tco```          
```scp -r "C:\Users\joonw\anaconda3\envs\jl2815\Lib\site-packages\GEMS_TCO" jl2815@amarel.rutgers.edu:/home/jl2815/tco```            # r stands for recursive, used to copy a folder.          


## Log in to Amarel HPC

```ssh jl2815@amarel.rutgers.edu```      
```module use /projects/community/modulefiles```  #without this, I can't load 2024.06-ts840         
```module load anaconda/2024.06-ts840```        
```conda activate gems_tco```       
```pip install -e /home/jl2815/tco/```     # this will install my package 'GEMS_TCO'       

### verify installation          
  
```pip list | grep GEMS_TCO```           # Verify installation        
```python -c "import GEMS_TCO; print('GEMS_TCO imported successfully')"```   

### Debugging when python and conda does not match.    
```which python``` gives ```/projects/community/anaconda/2024.06/ts840/bin/python```, so I am not using the python under ```gems_tco''' package.    
  
To make the change permanent, update your ```.bashrc```  
```nano ~/.bashrc```   
Replace every ```2023.10/bd387/base``` with ```2024.06/ts840```          # merely adding ```export PATH="/home/jl2815/.conda/envs/gems_tco/bin:$PATH"```  at the end of the line does not solve the problem   
Save the file and reload your shell:         
```source ~/.bashrc```        
Activate my environmnet again    
```conda activate gems_tco```   
```which python```    
Now you see the path: ```~/.conda/envs/gems_tco/bin/python```
