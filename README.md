## Python setting in mac     
- [Download Anaconda](https://www.anaconda.com/download)    
- Install git: type ```git``` on terminal and install command line tool   
  After installing Git, you need to set the configuration for your identity.   
  ```git config --global user.email "you@example.com"```     
  ```git config --global user.name "Your Name"```      
- [Install VScode](https://code.visualstudio.com/)   (recommended for ML and Statistics)
- Now you can clone respository from github    
- Create an environment. (see below)    
- Install GEMS_TCO package. (see below)    
- Install Pytorch package: Navigate to the current working proejct and then install pytorch.   
'''conda install pytorch torchvision torchaudio cpuonly -c pytorch'''     

## Creating and sharing environments in Python

-[Create and share environment on a local computer](install_python.md)   
-[Create ```gems_tco``` package](install_gems_tco_local.md)   

## Github Version Control
-[Sync with Microsoft VScode](github_version_control.md)

## AWS Setting
-[EC2, VS code, Environment set up](aws_ec2_vs_code_environment.md)     
-[aws guide](aws.md)   

## Rutgers Amarel (High Performance Cluster for Computing)

-[Create an environment on Rutgers Amarel](amarel_environment.md)      
-[Install ```gems_tco``` package on Amarel](install_mypackage_amarel.md)       

## C++ (visual studio + Resharper C++)

Select the DESKTOP DEVELOPMENT WITH C++ workload.

-[Download Resharper C++](https://www.jetbrains.com/resharper-cpp/download/download-thanks.html?platform=windows)

Make sure to select the C++ option. Then register JetBrains Product for students.

Installing Eigen (including unsupported Modules), gsl libraries. 

-[Download git](https://git-scm.com/downloads/win)

-Open the git bash and then install vcpkg, by running:        
git clone https://github.com/microsoft/vcpkg              

-Navigate to the vcpkg directory and bootstrap, by running:           
cd vcpkg       
./bootstrap-vcpkg.bat          

-Install Eigen, including unsupported modules, by running:                
./vcpkg install eigen3                        
-Integrate with Visual Studio, by running:                   
./vcpkg integrate install                        
-Use Eigen in your project:               
#include <Eigen/Dense>                  
#include <unsupported/Eigen/MatrixFunctions>                   

Similarly,       
./vcpkg install gsl             
./vcpkg integrate install                
#include <gsl/gsl_sf_bessel.h>                    
















