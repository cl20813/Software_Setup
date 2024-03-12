
# 
ssh jl2815@amarel.rutgers.edu 
wget https://ftp.pcre.org/pub/pcre/pcre2-10.35.tar.gz   
tar -zxf pcre2-10.35.tar.gz   
cd pcre2-10.35   
./configure --prefix=/home/jl2815/pcre/10.35   
make -j 8   
make install    
    
Add these lines to the end of your ~/.bashrc file 
(NOTE: the commands presented here assume you don't already have those environment variables set. If you do have them set already, adjust these lines accordingly):

vim ~/.bashrc   
(add end of the text)
export PATH=/home/jl2815/pcre/10.35/bin:$PATH
export C_INCLUDE_PATH=/home/jl2815/pcre/10.35/include
export CPLUS_INCLUDE_PATH=/home/jl2815/pcre/10.35/include
export LIBRARY_PATH=/home/jl2815/pcre/10.35/lib
export LD_LIBRARY_PATH=/home/jl2815/pcre/10.35/lib
export MANPATH=/home/jl2815/pcre/10.35/share/man:$MANPATH

:wq   then enter  to exit   

exit # (log out and log in again)   
ssh jl2815@amarel.rutgers.edu 



wget https://cran.r-project.org/src/base/R-4/R-4.1.0.tar.gz
tar -zxf R-4.1.0.tar.gz
cd R-4.1.0

awk '/> 7/ { c = 1 } !/> 7/ && c { print("  exit(0);"); c = 0; next; } 1' configure > configure.new && mv configure.new configure

./configure --prefix=/home/jl2815/R/4.1.0
make -j 8
make install
