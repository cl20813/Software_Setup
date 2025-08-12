## Installation
Download Anaconda [here](https://www.anaconda.com/download).
(Note: there are a variety of different python distributions; for statistics and machine learning, we recommend Anaconda.)

### Creating an environment 

1. Open Terminal
2. Create an environment called `jl2815` using `conda` with the command:
   ```conda create --name jl2815```
3. To install packages in your environment, first activate your environment:
   ```conda activate jl2815```
4. Then, install the following packages using the command:
   ```conda install numpy pandas matplotlib seaborn scikit-learn``` 
5. Install PyTorch by running the appropriate command from [here](https://pytorch.org) (for macOS, the command is: `conda install pytorch::pytorch torchvision torchaudio -c pytorch`
6. To exit your environment:
   ```conda deactivate```

Here is a helpful [cheatsheet](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) for `conda` environment commands.

### Share environment using .yml
1. mac:      
``` conda env export > /Users/joonwonlee/Documents/GEMS_TCO-1/faiss_env.yml```
    
2. Only include packages you've explicitly asekd for.
```conda env export --from-history >file.yml```

### Create an environment from an .yml file
1. Create an environment from an .yml file (the file has to be in the current working directory) :                      
mac:            
```conda env create --file /Users/joonwonlee/Documents/GEMS_TCO-1/faiss_env.yml```            
2. To verify that the new environment was installed correctly:               
```conda env list``` or  ```conda ifo --envs```        
3. Updating current working environment based on provided .yml file:              
```conda env update --prefix ./env --file environment.yml  --prune```             
4.Cloning an environment:                  
```conda create --name new_environment --clone existing_env```       
verify with             

### Installing packages in Jupyter notebook or Ipython environment.
1. conda install -c anaconda ipykernel    (this should be done in an active environment)   
2. ipython kernel install --user --name=<envname>             (ipython kernel install --user --name=jl2815)
     

