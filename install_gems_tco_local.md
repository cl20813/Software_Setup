# MAC

```conda activate gems_tco``` Don't for this if you want to make change in virtual environment.    
Go to command or terminal in VSCode and ```pip install --upgrade pip``` to use -e editable option.   
```cd /Users/joonwonlee/Documents/GEMS_TCO-1/src ```

Note that '''pyproject.toml''' and '''setup.py''' are located at /Users/joonwonlee/GEMS_TCO/.

``` /opt/anaconda3/envs/gems_tco/bin/python -m pip install -e . --use-pep517 ```

I need to use ```-e``` editable option so that any changes in my local repository that is cloned from github are reflected in my local package.

The --use-pep517 flag in the pip install command tells pip to use the PEP 517 build system. It allows for a more flexible and modern approach to building and installing packages, separate from the traditional setup.py method.

PEP 517 Compatibility: Ensures that the build process follows the standards defined in PEP 517, allowing you to use pyproject.toml for configuration.

The ```pyproject.toml file specifies the build system requirements and configuration```, while the ```setup.py file defines the package metadata and installation instructions```.

## If your environemnt still can't find the package then make sure to change your working directory.
Python's ability to locate modules indeed depends on the current working directory and sys.path. When your working directory is GEMS_TCO/exercise, Python might not be able to find the GEMS_TCO module because it's looking for it relative to that directory.

# Window:

Open the anaconda command prompt because environment 'jl2815' is under there

cd c:\\Users\\joonw\\TCO
pip install -e.      

for this code to work, there has to be ```setup.py``` and ```pyproject.toml``` in TCO, and ```GEMS_TCO package folder``` must be at the same level, in TCO.   
