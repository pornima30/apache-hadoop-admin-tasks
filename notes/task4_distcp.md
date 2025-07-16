'========================================
'     TASK 4: Distributed Copy (distcp)
'========================================

'-- Step 1: Setup S3 in core-site.xml (same as Task 1)

'-- Step 2: Update hadoop-env.sh
export HADOOP_CLASSPATH=$HADOOP_CLASSPATH:$HADOOP_HOME/share/hadoop/tools/lib/*

'-- Step 3: Add mapreduce classpath in mapred-site.xml
<property>
  <name>mapreduce.application.classpath</name>
  <value>
    $HADOOP_MAPRED_HOME/share/hadoop/mapreduce/*,
    $HADOOP_MAPRED_HOME/share/hadoop/mapreduce/lib/*,
    $HADOOP_MAPRED_HOME/share/hadoop/tools/lib/*
  </value>
</property>

'-- Step 4: Run distcp command (HDFS → S3)
hadoop distcp /user/hduser/hadoop-3.3.5.tar.gz s3a://clouderarepomy25/
