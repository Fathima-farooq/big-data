# commands

- HDFS is major component of the hadoop ecosystem which store all datasets of structured or unstructured data across various nodes

```bash
bsau@bsau-V530-15ICB:~$ cd hadoop-2.9.1
bsau@bsau-V530-15ICB:~/hadoop-2.9.1$ cd sbin

> To use the HDFS commands, first you need to start the Hadoop services using the following command:
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/sbin$ ./start-all.sh

> To check the Hadoop services are up and running use the following command:
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/sbin$ jps


> cr8 dir in hadoop's dfs:
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -mkdir /geeks  =>  '/' means absolute path
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -mkdir geeks2  =>   Relative path -> the folder will be created relative to the home directory.

> used to list all the files use lsr(recursively):
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -ls <path>
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -ls / => (list directories)

> touchz: It creates an empty file
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -touchz /sam/s.txt

> copyFromLocal (or) put: To copy files/folders from local file system to hdfs store.
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -copyFromLocal <local file path>  <dest(present on hdfs)>
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -copyFromLocal ../Desktop/AI.txt /geeks
(OR)
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -put ../Desktop/AI.txt /geeks

> copyToLocal (or) get: To copy files/folders from hdfs store to local file system
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -copyToLocal  <<srcfile(on hdfs)> <local file dest>
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -copyToLocal  /geeks   ../Desktop/hero
(OR)
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -get /geeks/myfile.txt  ../Desktop/hero

> moveFromLocal: This command will move file from local to hdfs.
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -moveFromLocal <local src>   <dest(on hdfs)>
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -moveFromLocal  ../Desktop/cutAndPaste.txt   /geeks

> cp: This command is used to copy files within hdfs
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -cp  <src(on hdfs)>  <dest(on hdfs)>
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs -cp /geeks  /geeks_copied

> mv: This command is used to move files within hdfs
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -mv  <src(on hdfs)> <src(on hdfs)>
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs  -mv  /geeks/myfile.txt  /geeks_copied

> rmr: This command deletes a file from HDFS recursively.
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -rmr <filename/directoryName>
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -rmr  /geeks_copied -> It will delete all the content inside the

> du: It will give the size of each file in directory
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -du  <dirName>
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -du /geeks

> dus:: This command will give the total size of directory/file (abv)
> stat: It will give the last modified time of directory or path (abv)

> cat: To print file contents
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -cat /sam/s.txt
```
