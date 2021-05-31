# Web Log Analysis through Scala Program

This project demostrates how to analyse Web Logs files through Scala Program. 


## Runing the Project in IntelliJ

CLone the project from Github into a local system. Eg. Ubuntu as follows:

git clone https://github.com/hsaberedo/WebLogAnalysisWithScala

![image](https://user-images.githubusercontent.com/66680663/120108651-12b6f980-c15e-11eb-9022-46214531a38a.png)



Once the cloning is complete, you can start gui Intellij installed on the same platform and open the project as shown below:


![image](https://user-images.githubusercontent.com/66680663/120108737-72150980-c15e-11eb-961b-b3aa8faf71bd.png)


And Run the project as shown below:

![image](https://user-images.githubusercontent.com/66680663/120108935-39c1fb00-c15f-11eb-8945-ddfa10aec636.png)

On successful completion, an exit code of 0 is displayed:

![image](https://user-images.githubusercontent.com/66680663/120111639-a42c6880-c16a-11eb-94e6-c68da122fcee.png)


And you can check the Reports Directories to see the json format reports:

![image](https://user-images.githubusercontent.com/66680663/120124902-66513380-c1ae-11eb-93da-bc0e08f6c6e8.png)


**1. Dates and Connection Counts Report:**

_**All the dates having too big number of connection (> 20000)**_

![image](https://user-images.githubusercontent.com/66680663/120124973-aadccf00-c1ae-11eb-8611-119da46d301d.png)


**2. URI Based Report:**

_**Computing list of number of access by URI for each URI**_

![image](https://user-images.githubusercontent.com/66680663/120125038-e5466c00-c1ae-11eb-81af-20d737ddd981.png)


**3. IP Based Report:**

_**Computing list of number of access per IP address for each IP address**_

![image](https://user-images.githubusercontent.com/66680663/120125178-83d2cd00-c1af-11eb-9de0-10a8adc84f60.png)

![image](https://user-images.githubusercontent.com/66680663/120125088-23dc2680-c1af-11eb-9577-c38cc90b33cf.png)


## How to run the program locally


## Packaging 

To package the project:

On the local unix system:

```bash
sbt assembly
```
![](cdn/1.png)

## Deploying the program:

Upload OR Copy the fatjar to the desired target location

```
TARGET_LOCATION=<directory_location>
cp target/scala-2.12/spark-sbt-template-assembly-1.0.jar $TARGET_LOCATION
```

![](cdn/2.png)

```
JAR_PATH=$(pwd)/target/scala-2.12/spark-sbt-template-assembly-1.0.jar
spark-submit --master=local[*] --deploy-mode client --class App $JAR_PATH
```

![](cdn/3.png)

Ensure that the App.run file is included as shown below:

![image](https://user-images.githubusercontent.com/66680663/120112002-f8841800-c16b-11eb-8c5e-b159189a2bf5.png)




