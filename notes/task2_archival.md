'========================================
'     TASK 2: Hadoop Archive (.har)
'========================================

'-- Step 1: Create archive from existing folder
hadoop archive -archiveName myarch.har -p /user/ubuntu /user/hduser

'-- Step 2: Verify archive structure
hdfs dfs -ls -R har:///user/hduser/myarch.har

'-- Step 3: Extract specific file from archive
hdfs dfs -cp har:///user/hduser/myarch.har/abc /user/hduser/unarch
