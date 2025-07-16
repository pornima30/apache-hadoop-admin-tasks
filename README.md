# Apache Hadoop Admin Tasks

This project contains hands-on Apache Hadoop administration tasks performed as part of my training and project work.

## 📁 Project Structure

| Folder | Contents |
|--------|----------|
| `scripts/` | Collected shell commands from lectures and practical sessions |
| `terminal-history/` | Raw terminal history during setup and task execution |
| `screenshots/` | Visual evidence of task completion |
| `notes/` | Explanations of key tasks and steps taken |

## 🔧 Covered Tasks

- S3 to HDFS file transfer using `fs -cp` and `distcp`
- Hadoop Archival using `.har` format
- Trash management & checkpoint configuration
- Setting replication factors
- Distributed copy to S3
- Customizing block size

## 🛠️ Tools Used

- Hadoop 3.3.5
- Amazon S3 (via S3A connector)
- Ubuntu EC2 Instance
- HDFS, YARN, MapReduce

## ✨ Sample Commands

```bash
hadoop distcp /user/hduser/hadoop-3.3.5.tar.gz s3a://clouderarepomy25/
hdfs dfs -setrep -w 4 /user/hduser/abc
hadoop archive -archiveName myarch.har -p /user/ubuntu /user/hduser
