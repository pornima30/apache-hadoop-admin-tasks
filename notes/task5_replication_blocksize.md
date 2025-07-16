'=================================================
'     TASK 5: Replication Factor & Block Size
'=================================================

'-- Step 1: Set block size in hdfs-site.xml
<property>
  <name>dfs.block.size</name>
  <value>256m</value>
</property>

'-- Step 2: Set replication factor for a file
hdfs dfs -setrep -w 4 /user/hduser/abc
