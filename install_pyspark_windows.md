# https://www.datacamp.com/tutorial/installation-of-pyspark

Pyspark = Python + Apache Spark      
Apache Spark is a new and open-source framework used in the big data industry for real-time processing and batch processing.    

## Pre-requisite installation is Python. 

## Java installation. In my case, it's Windows 64-bit.
1. Download Java [here](https://www.oracle.com/java/technologies/downloads/)   
2. Go to "Command Prompt" and type "java -version" (space between java and -) to know the version and know whether it is installed or not.    
3. Copy Java path. In my case, "C:\Program Files\Java\jdk-21".   
4. Go to search bar and "Edit the system environment"   
5. Click into the "Environment Variables".   
6. Click into "New" and use variable name as "JAVA_HOME" and copy paste java path into variable value. Then click 'Ok'.   
7. Add the variable name as "PATH" and path value as "C:\Program Files\Java\jdk-21\bin", which is your location of Java bin file. Click 'OK'.   

## Installing Pyspark
1. Go to Apache Spark [here](https://spark.apache.org/downloads.html).   
2. Select the Spark release and package type and download the .tgz file in the third row.
3. Make a new folder called 'spark' in the C directory and extract the given file by using "Winrar".
4. Go to [Winutils](https://github.com/steveloughran/winutils) choose your previously downloaded Hadoop version in 3. Then download the winutils.exe file by going inside 'bin'.
5. Make a new folder in the C directory called 'winutil's and inside of it creage again a new folder called 'bin'. Then put the file recently downloaded 'winutils' inside it.
6. Again, search "Edit the system environment" and create a new environment where variable name as 'hadoop_home' and variable value to be the location of winutils, which is "C:\winutils" and click "ok".
7. For spark, create a new environment where variable name is "Spark_home" and the variable value to be the location of spark, "C:\spark" and click "ok".
8. Finally double click the 'Path' in system variables and click "new" and copy paste "%Spark_Home%\bin" and click Okay. Where a new path is created.

## You can verify the paths "echo %PYTHONPATH%" in prompt command. 

## Finalizing Pyspark installation
1. Open command pormpt and type C:\Users\joonw>pyspark




