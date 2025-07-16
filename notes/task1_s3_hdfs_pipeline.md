'==============================================
'     TASK 1: S3 ↔ HDFS Pipeline Configuration
'==============================================

'-- Step 1: Edit core-site.xml to add S3 credentials
<property>
  <name>fs.s3a.access.key</name>
  <value>YOUR_ACCESS_KEY</value>
</property>

<property>
  <name>fs.s3a.secret.key</name>
  <value>YOUR_SECRET_KEY</value>
</property>

<property>
  <name>fs.s3.impl</name>
  <value>org.apache.hadoop.fs.s3.S3FileSystem</value>
</property>

'-- Step 2: Update hadoop-env.sh
export HADOOP_CLASSPATH=$HADOOP_CLASSPATH:$HADOOP_HOME/share/hadoop/tools/lib/*

'-- Step 3: Copy file from S3 to HDFS
hdfs dfs -cp s3a://<bucket-name>/<filename> /user/hduser/

'-- Step 4: Copy file from HDFS to S3
hadoop fs -cp /user/hduser/<filename> s3a://<bucket-name>/
