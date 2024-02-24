

Pyspark = Python + Apache Spark      
Apache Spark is a new and open-source framework used in the big data industry for real-time processing and batch processing.    



## Java installation. In my case, it's Windows 64-bit.
1. Download Java [here](https://www.oracle.com/java/technologies/downloads/)   
2. Go to "Command Prompt" and type "java -version" (space between java and -) to know the version and know whether it is installed or not.    
3. Copy Java path. In my case, "C:\Program Files\Java\jdk-21".   
4. Go to search bar and "Edit the system environment"   
5. Click into the "Environment Variables".   
6. Click into "New" in User variables and use variable name as "JAVA_HOME" and copy paste java path into variable value. Then click 'Ok'.   
7. Add the variable name as "PATH" and path value as "C:\Program Files\Java\jdk-21\bin", which is your location of Java bin file. Click 'OK'.

## Python installation
If you have installed Python via Anaconda, I suggest to download Python from their official website. [here](https://www.python.org/downloads/)   
Make sure!! Check box to add Python to PATH during installation. If you double click the PATH in Users variables, you see the python path and java path as well.  
Example:   
1) C:\Users\joonw\AppData\Local\Programs\Python\Python312\Scripts\  
2) C:\Users\joonw\AppData\Local\Programs\Python\Python312\   
3) C:\Users\joonw\AppData\Local\Programs\Python\Launcher\
4) C:\Program Files\Java\jdk-21\bin

## Installing Pyspark
1. Go to Apache Spark [here](https://spark.apache.org/downloads.html).   
2. Select the Spark release and package type and download the .tgz file in the third row.                     ex) "Spark 3.5 and hadoop 3.3. and later".           
3. Make a new folder called 'spark' in the C directory and extract the given file by using "Winrar". Then create a new environment where variable name is "SPARK_HOME" in the User Variables (you can do it in system variables but has to be consistent).
   ex)C:\spark\spark-3.5.0-bin-hadoop3              
5. Go to [Winutils](https://github.com/cdarlint/winutils) choose your previously downloaded Hadoop version in 3.35 Then download the winutils.exe file by going inside 'bin'. Hadoop is not natively supported on Windows so we need to use a utility called 'winutils.exe' to run Spark.   
6. Then put the file recently downloaded 'winutils' into SPARK_HOME.             ex) C:\spark\spark-3.5.0-bin-hadoop3         
7. Again, search "Edit the system environment" and create a new environment where variable name as 'HADOOP_HOME' and variable value to be the same as SPARK_HOME in User Variables.   ex) C:\spark\spark-3.5.0-bin-hadoop3             
9. Finally double click the 'Path' in system variables and click "new" and copy paste "%Spark_Home%\bin" and %HADOOP_HOME%bin. Then click Okay. Where a new path is created.              

## You can verify the paths "echo %PYTHONPATH%" in prompt command. 

## Finalizing Pyspark installation
1. pip install findspark            
1. Open Useres command pormpt and type C:\Users\joonw>pyspark            

import findspark   
findspark.init()              
from pyspark import SparkConf, SparkContext            

## reference 
[datacamp, a little old one](https://www.datacamp.com/tutorial/installation-of-pyspark)             
[second reference](https://www.machinelearningplus.com/pyspark/install-pyspark-on-windows/)                         



