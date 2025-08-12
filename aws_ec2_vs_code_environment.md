
## Launch Instance
Go to EC2 and then click ```launch instance```

Name and tags: ```gems_tco```   
```Amazon Linux 2023 AMI Kernel 6.1```   
```64-bit(x86)``` (arcithecture that is optimized for cpu process)      
Instance type: ```c6i.2xlarge```      
key_pair (login) create a new key called ```gems_tco_key```, and save it in the download directory. Then 
```chmod 400 /Users/joonwonlee/Documents/AWS/gems_tco_key.pem``` just for once for each key.     

Security: ```Allow ssh traffic from my IP: 128.6.147.81/32```  81/32 use either one, and if my mac IP changes, then go to  

Inbound rules - Edit inbound rules - ```type:ssh, source:MY IP, 128.6.147.81/32``` and then click save rules.  

## Connect VS-Code
### Elastic IP
Go to  Elastic IPs in EC2 and then allocate default - action - associate instance.

### VS code
On the left, click remote explorer - enter ```ssh ec2-user@52.21.144.182```, this is public or elastic IP. Then open configuration file and type:

Host AWS_EC2     
     HostName 52.21.144.182 # note that we can use elastic ip here but use private ip for ```ssh ec2-user@172.31.44.24```    
     User ec2-user (default)     
     IdentifyFile /Users/joonwonlee/Documents/AWS/gems_tco_key.pem (I generated and saved the key file when lanuching the instance above -key_pair      

## COMMON ERROR WHEN TERMINATE AND RECREATE INSTANCE, WHEN THE INSTANCE WAS REBUILT, SSH FINGER PRINT CHANGED    
You can also remove the entry by IP:    
```ssh-keygen -R 52.21.144.182``` 

## Clone git repository
     
## Python environment in EC2    
```mkdir env```        
```cd env```                
```python3 -m venv gems_tco_env```    #venv use the same python version that is used on the system       
```cd ```       
```source ./env/gems_tco_env/bin/activate```        

```/home/ec2-user/env/gems_tco_env/bin/python3 -m pip install --upgrade pip```       
```pip install faiss-cpu pybind11 numpy pandas matplotlib seaborn scikit-learn xarray netCDF4 typer```        
```pip install torch torchvision torchaudio```    # Note: This is the equivalent of the conda command but specifically for a CPU.)       

```sudo yum install git -y``` install git   
```pip install git+https://github.com/patrick-kidger/torchcubicspline.git```   

### Install my package gems_tco   
```cd /home/ec2-user/GEMS_TCO/src```     
```sudo yum install python3-pip -y```         
```pip install -e . --use-pep517```        
```pip install ipykernel```      

### Compile c++ file   
```cd /home/ec2-user/GEMS_TCO/src/GEMS_TCO/cpp_src```  
```sudo yum groupinstall "Development Tools" -y```     
```sudo dnf install python3-devel -y```  # python development header    
```c++ -O3 -Wall -shared -std=c++11 -fPIC $(python3 -m pybind11 --includes) maxmin_ancestor.cpp -o ../maxmin_ancestor_cpp.so```   
```c++ -O3 -Wall -shared -std=c++11 -fPIC $(python3 -m pybind11 --includes) maxmin.cpp -o ../maxmin_cpp.so```     



     
