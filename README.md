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


1. **Packaging **

To package the project:

Run sbt assembly to create single, executable JAR file:

```bash
$ sbt assembly
```
![](cdn/1.png)

And below is the screen shot of the sbt assemply:

![image](https://user-images.githubusercontent.com/66680663/120146038-636d3780-c1dc-11eb-8c25-b64370c1f9e5.png)

2. **Next, run the JAR file:**

```
TARGET_AREA=<directory_path>
cp target/scala-2.12/spark-sbt-template-assembly-1.0.jar $TARGET_AREA
```

```
JAR_AREA=$(pwd)/target/scala-2.12/spark-sbt-template-assembly-1.0.jar
spark-submit --master=local[*] --deploy-mode client --class App $JAR_AREA
```


## Deploying the Project on AWS

You need to upload the access log file unto AWS S3 Bucket as shown below. This is achieved by clicking on **"Upload"** then **"Add Files"** from the S3 Bucket console in the imabe below: 

![image](https://user-images.githubusercontent.com/66680663/120223394-6fd3ad80-c239-11eb-9909-49a0bbe16eee.png)



and the generate fatjar to s3.



