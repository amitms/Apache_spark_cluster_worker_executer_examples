requires setup of apache hadoop installation. Apache spark will run as standalone cluster
```
curl https://dlcdn.apache.org/hadoop/common/hadoop-3.3.6/hadoop-3.3.6.tar.gz
tar -xvf hadoop-3.3.6.tar.gz
cd hadoop-3.3.6
bin/hadoop
curl https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-BD0225EN-SkillsNetwork/labs/data/data.txt --output data.txt
bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-3.3.6.jar wordcount data.txt output
ls output
cat  output/part-r-00000
```
spark config file spark-defaults.conf.template rename it to spark-defaults.conf and put in /conf folder
Spark master and worker start
```
./sbin/start-master.sh
https://amitms2005-8080.theiadockernext-1-labs-prod-theiak8s-4-tor01.proxy.cognitiveclass.ai/

export JAVA_HOME=/usr/lib/jvm/java-1.11.0-openjdk-amd64
export SPARK_HOME=/home/project/spark-3.3.3-bin-hadoop3
./sbin/start-worker.sh spark://theiadocker-yourname:7077 --cores 1 --memory 1g

touch submit.py
export JAVA_HOME=/usr/lib/jvm/java-1.11.0-openjdk-amd64
export SPARK_HOME=/home/project/spark-3.3.3-bin-hadoop3
pip3 install findspark
python3 submit.py

$SPARK_HOME/sbin/stop-master.sh
$SPARK_HOME/sbin/stop-workers.sh
```
spark UI: https://<driver-node>:4040  master and worker ports are different
spark-defaults.conf.template
![spark UI](https://github.com/user-attachments/assets/3631a84f-f362-4c24-b958-ceba585ecc6f)
![WORKER](https://github.com/user-attachments/assets/dea98f1f-a873-4826-a720-a5366a0628ba)
