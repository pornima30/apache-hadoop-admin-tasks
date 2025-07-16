'==========================================
'     TASK 3: Trash & Checkpoint Setup
'==========================================

'-- Step 1: Edit core-site.xml
<property>
  <name>fs.trash.interval</name>
  <value>30</value>
  <description>Time (minutes) before file is deleted from Trash</description>
</property>

<property>
  <name>fs.trash.checkpoint.interval</name>
  <value>15</value>
</property>

'-- Step 2: Delete with trash
hdfs dfs -rm /user/hduser/abc

'-- Step 3: Permanent delete
hdfs dfs -rm -skipTrash /user/hduser/abc
