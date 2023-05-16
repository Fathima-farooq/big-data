```bash
bsau@bsau-V530-15ICB:~$ cd hadoop-2.9.1
bsau@bsau-V530-15ICB:~/hadoop-2.9.1$ cd sbin

bsau@bsau-V530-15ICB:~/hadoop-2.9.1/sbin$ ./start-all.sh
This script is Deprecated. Instead use start-dfs.sh and start-yarn.sh
Starting namenodes on [localhost]
localhost: starting namenode, logging to /home/bsau/hadoop-2.9.1/logs/hadoop-bsau-namenode-bsau-V530-15ICB.out
localhost: starting datanode, logging to /home/bsau/hadoop-2.9.1/logs/hadoop-bsau-datanode-bsau-V530-15ICB.out
Starting secondary namenodes [0.0.0.0]
0.0.0.0: starting secondarynamenode, logging to /home/bsau/hadoop-2.9.1/logs/hadoop-bsau-secondarynamenode-bsau-V530-15ICB.out
starting yarn daemons
starting resourcemanager, logging to /home/bsau/hadoop-2.9.1/logs/yarn-bsau-resourcemanager-bsau-V530-15ICB.out
localhost: starting nodemanager, logging to /home/bsau/hadoop-2.9.1/logs/yarn-bsau-nodemanager-bsau-V530-15ICB.out

bsau@bsau-V530-15ICB:~/hadoop-2.9.1/sbin$ jps
5010 ResourceManager
4451 NameNode
4645 DataNode
4860 SecondaryNameNode
8989 Jps
5166 NodeManager

bsau@bsau-V530-15ICB:~/hadoop-2.9.1/sbin$ cd ..
bsau@bsau-V530-15ICB:~/hadoop-2.9.1$ cd bin

bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -mkdir /jay
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ nano jaya.csv
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ pwd jaya.csv
/home/bsau/hadoop-2.9.1/bin
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ hdfs dfs -put '/home/bsau/hadoop2.9.1/bin/jaya.csv' /jay
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ nano mapper1.py
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ pwd mapper1.py
/home/bsau/hadoop-2.9.1/bin
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ nano reducer2.py
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ cat '/home/bsau/hadoop-2.9.1/bin/jaya.csv'|
python3 mapper1.py| python3 reducer.py
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$
```

```py
#!/usr/bin/python
import sys
#input comes from STDIN (standard input)for line in sys.stdin:
    line = line.strip()
    line = line.split(",")
    if len(line) >=2:
        sex = line[1]
        age = line[2]
        print('%s\t%s' % (sex, age))
```

```py
#!/usr/bin/python
#reducer2.py
import sys
sex_age = {}
#Partioner
for line in sys.stdin:
    line = line .strip()
    sex, age = line.split('\t')
    if sex in sex_age:
        sex_age[sex].append(int(age))
    else:
        sex_age[sex] = []
        sex_age[sex].append(int(age))
#reducer
for sex in sex_age.keys():
    ave_age = sum(sex_age[sex])*1.0 / len(sex_age[sex])
    print ('%s\t%s'% (sex, ave_age))
```

```csv
"00003",1,21,72,180,3,1
"00004",2,32,63,135,1,2
"00009",2,48,61,147,1,2
"00010",1,35,70,205,1,2
"00011",1,48,67,170,3,3
"00019",1,44,70,187,3,3
"00034",2,42,63,128,1,2
"00040",2,17,60,100,3,3
"00044",2,24,66,125,3,2
"00045",2,67,64,147,3,3
"00048",2,56,68,231,1,2
"00049",2,82,73,97,2,1
"00051",1,44,71,300,1,2
```
