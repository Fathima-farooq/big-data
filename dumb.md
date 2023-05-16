Spark installation 
go to apache spark websit and download spark
ri8 click download file and select extract here
go into extracted file then -> bin -> select spark-shell then copy it and paste in terminal => scala in terminal (ctrl + c) to get out

Scala installation
sudo apt install scala


nano samreen.scala
wri
scala samreen.scala


////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

<!-- Hive installation -->

/home/bsau/Downloads/apache-hive-3.1.3-bin.tar.gz


bsau@bsau-V530-15ICB:~$ cd  hadoop-2.9.1 
bsau@bsau-V530-15ICB:~/hadoop-2.9.1$ cd sbin
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/sbin$ ./start-all.sh
This script is Deprecated. Instead use start-dfs.sh and start-yarn.sh
Starting namenodes on [localhost]
^[[Alocalhost: starting namenode, logging to /home/bsau/hadoop-2.9.1/logs/hadoop-bsau-namenode-bsau-V530-15ICB.out
localhost: starting datanode, logging to /home/bsau/hadoop-2.9.1/logs/hadoop-bsau-datanode-bsau-V530-15ICB.out
Starting secondary namenodes [0.0.0.0]
0.0.0.0: starting secondarynamenode, logging to /home/bsau/hadoop-2.9.1/logs/hadoop-bsau-secondarynamenode-bsau-V530-15ICB.out
starting yarn daemons
starting resourcemanager, logging to /home/bsau/hadoop-2.9.1/logs/yarn-bsau-resourcemanager-bsau-V530-15ICB.out
localhost: starting nodemanager, logging to /home/bsau/hadoop-2.9.1/logs/yarn-bsau-nodemanager-bsau-V530-15ICB.out
<!-- Pasted hive inside apache hive inside bin inside hive file link copied in downloads -->
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/sbin$ /home/bsau/Downloads/apache-hive-3.1.3-bin/bin/hive
SLF4J: Class path contains multiple SLF4J bindings.
SLF4J: Found binding in [jar:file:/home/bsau/Downloads/apache-hive-3.1.3-bin/lib/log4j-slf4j-impl-2.17.1.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: Found binding in [jar:file:/home/bsau/hadoop-2.9.1/share/hadoop/common/lib/slf4j-log4j12-1.7.25.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: See http://www.slf4j.org/codes.html#multiple_bindings for an explanation.
SLF4J: Actual binding is of type [org.apache.logging.slf4j.Log4jLoggerFactory]
Hive Session ID = 26dbe16e-6328-4982-bee8-163527b3921d

Logging initialized using configuration in jar:file:/home/bsau/Downloads/apache-hive-3.1.3-bin/lib/hive-common-3.1.3.jar!/hive-log4j2.properties Async: true
Hive-on-MR is deprecated in Hive 2 and may not be available in the future versions. Consider using a different execution engine (i.e. spark, tez) or using Hive 1.X releases.
hive> 

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
bash: export: `/usr/lib/jvm/java-8-oracle/': not a valid identifier
bash: export: `home/bsau/apache-hive-3.1.3-bin/': not a valid identifier
bsau@bsau-V530-15ICB:~$ /home/bsau/spark-3.3.2-bin-hadoop3/bin/spark-shell
23/04/10 14:05:12 WARN Utils: Your hostname, bsau-V530-15ICB resolves to a loopback address: 127.0.1.1; using 172.20.105.72 instead (on interface enp1s0)
23/04/10 14:05:12 WARN Utils: Set SPARK_LOCAL_IP if you need to bind to another address
Setting default log level to "WARN".
To adjust logging level use sc.setLogLevel(newLevel). For SparkR, use setLogLevel(newLevel).
23/04/10 14:05:17 WARN NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
Spark context Web UI available at http://172.20.105.72:4040
Spark context available as 'sc' (master = local[*], app id = local-1681115719157).
Spark session available as 'spark'.
Welcome to
      ____              __	
     / __/__  ___ _____/ /__
    _\ \/ _ \/ _ `/ __/  '_/
   /___/ .__/\_,_/_/ /_/\_\   version 3.3.2
      /_/
         
Using Scala version 2.12.15 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_202)
Type in expressions to have them evaluated.
Type :help for more information.

scala>^Cbsau@bsau-V530-15ICB:~$ nano sam.scala
Code:                                                                                              
    object ScalaExample{
        def main(args:Array[String]){
            println("Hello Scala")
        }
    }
otp: Hello Scala

bsac@bsac-HP-280-Pro-G8-Microtower-PC:~/hadoop-2.9.1/sbin$ jps
4880 NodeManager
4196 NameNode
4566 SecondaryNameNode
4360 DataNode
5228 Jps
4735 ResourceManager
bsac@bsac-HP-280-Pro-G8-Microtower-PC:~/hadoop-2.9.1/sbin$ cd sbin
bash: cd: sbin: No such file or directory
bsac@bsac-HP-280-Pro-G8-Microtower-PC:~/hadoop-2.9.1/sbin$ cd ..
bsac@bsac-HP-280-Pro-G8-Microtower-PC:~/hadoop-2.9.1$ cd bin
bsac@bsac-HP-280-Pro-G8-Microtower-PC:~/hadoop-2.9.1/bin$ hive

Logging initialized using configuration in jar:file:/home/bsac/apache-hive-1.2.2-bin/lib/hive-common-1.2.2.jar!/hive-log4j.properties
hive> CREATE DATABASE HIVE;
OK
Time taken: 0.798 seconds
hive> CREATE DATABASE STUDENTS;
OK
Time taken: 0.071 seconds
hive> SHOW DATABASES;
OK
default
hive
students
Time taken: 0.261 seconds, Fetched: 3 row(s)
hive> CREATE TABLE STUD_DB;
FAILED: SemanticException [Error 10043]: Either list of columns or a custom serializer should be specified
hive> USE STUDENTS;
OK
Time taken: 0.007 seconds
hive> CREATE TABLE DETAILS;
FAILED: SemanticException [Error 10043]: Either list of columns or a custom serializer should be specified
hive> DESCRIBE DATABASE STUDENTS;
OK
students		hdfs://localhost:50000/user/hive/warehouse/students.db	bsac	USER	
Time taken: 0.023 seconds, Fetched: 1 row(s)
hive> DROP DATABASE IF EXISTS HIVE;
OK
Time taken: 0.542 seconds
hive> SHOW DATABASES;
OK
default
students
Time taken: 0.025 seconds, Fetched: 2 row(s)
hive> CREATE TABLE STUDETAILS(SNO INT,SNAME STRING,SMARKS INT,);
NoViableAltException(307@[])
	at org.apache.hadoop.hive.ql.parse.HiveParser_IdentifiersParser.identifier(HiveParser_IdentifiersParser.java:10858)
	at org.apache.hadoop.hive.ql.parse.HiveParser.identifier(HiveParser.java:45918)
	at org.apache.hadoop.hive.ql.parse.HiveParser.columnNameType(HiveParser.java:38119)
	at org.apache.hadoop.hive.ql.parse.HiveParser.columnNameTypeList(HiveParser.java:36278)
	at org.apache.hadoop.hive.ql.parse.HiveParser.createTableStatement(HiveParser.java:5217)
	at org.apache.hadoop.hive.ql.parse.HiveParser.ddlStatement(HiveParser.java:2643)
	at org.apache.hadoop.hive.ql.parse.HiveParser.execStatement(HiveParser.java:1653)
	at org.apache.hadoop.hive.ql.parse.HiveParser.statement(HiveParser.java:1112)
	at org.apache.hadoop.hive.ql.parse.ParseDriver.parse(ParseDriver.java:202)
	at org.apache.hadoop.hive.ql.parse.ParseDriver.parse(ParseDriver.java:166)
	at org.apache.hadoop.hive.ql.Driver.compile(Driver.java:397)
	at org.apache.hadoop.hive.ql.Driver.compile(Driver.java:309)
	at org.apache.hadoop.hive.ql.Driver.compileInternal(Driver.java:1145)
	at org.apache.hadoop.hive.ql.Driver.runInternal(Driver.java:1193)
	at org.apache.hadoop.hive.ql.Driver.run(Driver.java:1082)
	at org.apache.hadoop.hive.ql.Driver.run(Driver.java:1072)
	at org.apache.hadoop.hive.cli.CliDriver.processLocalCmd(CliDriver.java:213)
	at org.apache.hadoop.hive.cli.CliDriver.processCmd(CliDriver.java:165)
	at org.apache.hadoop.hive.cli.CliDriver.processLine(CliDriver.java:376)
	at org.apache.hadoop.hive.cli.CliDriver.executeDriver(CliDriver.java:736)
	at org.apache.hadoop.hive.cli.CliDriver.run(CliDriver.java:681)
	at org.apache.hadoop.hive.cli.CliDriver.main(CliDriver.java:621)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.apache.hadoop.util.RunJar.run(RunJar.java:239)
	at org.apache.hadoop.util.RunJar.main(RunJar.java:153)
FAILED: ParseException line 1:56 cannot recognize input near ')' '<EOF>' '<EOF>' in column specification
hive> CREATE TABLE STUDETAILS(SNO INT,SNAME STRING,SMARKS INT);
OK
Time taken: 0.347 seconds
hive> SHOW TABLES;
OK
studetails
Time taken: 0.022 seconds, Fetched: 1 row(s)
hive> DESCRIBE STUDETAILS;
OK
sno                 	int                 	                    
sname               	string              	                    
smarks              	int                 	                    
Time taken: 0.39 seconds, Fetched: 3 row(s)
hive> INSERT INTO TABLE STUDETAILS(111,ANA,87),(112,BALA,76),(113,CATHERIN,89),(114,DAVID,66),(115,EMILY,89),(116,FARHAN,56),(117,HARITHA,78);
NoViableAltException(302@[])
	at org.apache.hadoop.hive.ql.parse.HiveParser_IdentifiersParser.identifier(HiveParser_IdentifiersParser.java:10858)
	at org.apache.hadoop.hive.ql.parse.HiveParser.identifier(HiveParser.java:45918)
	at org.apache.hadoop.hive.ql.parse.HiveParser.columnName(HiveParser.java:36665)
	at org.apache.hadoop.hive.ql.parse.HiveParser.columnNameList(HiveParser.java:36528)
	at org.apache.hadoop.hive.ql.parse.HiveParser.insertClause(HiveParser.java:44680)
	at org.apache.hadoop.hive.ql.parse.HiveParser.regularBody(HiveParser.java:41270)
	at org.apache.hadoop.hive.ql.parse.HiveParser.queryStatementExpressionBody(HiveParser.java:40488)
	at org.apache.hadoop.hive.ql.parse.HiveParser.queryStatementExpression(HiveParser.java:40358)
	at org.apache.hadoop.hive.ql.parse.HiveParser.execStatement(HiveParser.java:1593)
	at org.apache.hadoop.hive.ql.parse.HiveParser.statement(HiveParser.java:1112)
	at org.apache.hadoop.hive.ql.parse.ParseDriver.parse(ParseDriver.java:202)
	at org.apache.hadoop.hive.ql.parse.ParseDriver.parse(ParseDriver.java:166)
	at org.apache.hadoop.hive.ql.Driver.compile(Driver.java:397)
	at org.apache.hadoop.hive.ql.Driver.compile(Driver.java:309)
	at org.apache.hadoop.hive.ql.Driver.compileInternal(Driver.java:1145)
	at org.apache.hadoop.hive.ql.Driver.runInternal(Driver.java:1193)
	at org.apache.hadoop.hive.ql.Driver.run(Driver.java:1082)
	at org.apache.hadoop.hive.ql.Driver.run(Driver.java:1072)
	at org.apache.hadoop.hive.cli.CliDriver.processLocalCmd(CliDriver.java:213)
	at org.apache.hadoop.hive.cli.CliDriver.processCmd(CliDriver.java:165)
	at org.apache.hadoop.hive.cli.CliDriver.processLine(CliDriver.java:376)
	at org.apache.hadoop.hive.cli.CliDriver.executeDriver(CliDriver.java:736)
	at org.apache.hadoop.hive.cli.CliDriver.run(CliDriver.java:681)
	at org.apache.hadoop.hive.cli.CliDriver.main(CliDriver.java:621)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.apache.hadoop.util.RunJar.run(RunJar.java:239)
	at org.apache.hadoop.util.RunJar.main(RunJar.java:153)
FAILED: ParseException line 1:29 cannot recognize input near '111' ',' 'ANA' in column name
hive> INSERT INTO TABLE STUDETAILS(111,'ANA',87),(112,'BALA',76),(113,'CATHERIN',89),(114,'DAVID',66),(115,'EMILY',89),(116,'FARHAN',56),(117,'HARITHA',78);
NoViableAltException(302@[])
	at org.apache.hadoop.hive.ql.parse.HiveParser_IdentifiersParser.identifier(HiveParser_IdentifiersParser.java:10858)
	at org.apache.hadoop.hive.ql.parse.HiveParser.identifier(HiveParser.java:45918)
	at org.apache.hadoop.hive.ql.parse.HiveParser.columnName(HiveParser.java:36665)
	at org.apache.hadoop.hive.ql.parse.HiveParser.columnNameList(HiveParser.java:36528)
	at org.apache.hadoop.hive.ql.parse.HiveParser.insertClause(HiveParser.java:44680)
	at org.apache.hadoop.hive.ql.parse.HiveParser.regularBody(HiveParser.java:41270)
	at org.apache.hadoop.hive.ql.parse.HiveParser.queryStatementExpressionBody(HiveParser.java:40488)
	at org.apache.hadoop.hive.ql.parse.HiveParser.queryStatementExpression(HiveParser.java:40358)
	at org.apache.hadoop.hive.ql.parse.HiveParser.execStatement(HiveParser.java:1593)
	at org.apache.hadoop.hive.ql.parse.HiveParser.statement(HiveParser.java:1112)
	at org.apache.hadoop.hive.ql.parse.ParseDriver.parse(ParseDriver.java:202)
	at org.apache.hadoop.hive.ql.parse.ParseDriver.parse(ParseDriver.java:166)
	at org.apache.hadoop.hive.ql.Driver.compile(Driver.java:397)
	at org.apache.hadoop.hive.ql.Driver.compile(Driver.java:309)
	at org.apache.hadoop.hive.ql.Driver.compileInternal(Driver.java:1145)
	at org.apache.hadoop.hive.ql.Driver.runInternal(Driver.java:1193)
	at org.apache.hadoop.hive.ql.Driver.run(Driver.java:1082)
	at org.apache.hadoop.hive.ql.Driver.run(Driver.java:1072)
	at org.apache.hadoop.hive.cli.CliDriver.processLocalCmd(CliDriver.java:213)
	at org.apache.hadoop.hive.cli.CliDriver.processCmd(CliDriver.java:165)
	at org.apache.hadoop.hive.cli.CliDriver.processLine(CliDriver.java:376)
	at org.apache.hadoop.hive.cli.CliDriver.executeDriver(CliDriver.java:736)
	at org.apache.hadoop.hive.cli.CliDriver.run(CliDriver.java:681)
	at org.apache.hadoop.hive.cli.CliDriver.main(CliDriver.java:621)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.apache.hadoop.util.RunJar.run(RunJar.java:239)
	at org.apache.hadoop.util.RunJar.main(RunJar.java:153)
FAILED: ParseException line 1:29 cannot recognize input near '111' ',' ''ANA'' in column name
hive> INSERT INTO TABLE STUDETAILS(111,'ADIL',87),(112,'BALA',76),(113,'CATHERIN',89),(114,'DAVID',66),(115,'EMILY',89),(116,'FARHAN',56),(117,'HARITHA',78);
NoViableAltException(302@[])
	at org.apache.hadoop.hive.ql.parse.HiveParser_IdentifiersParser.identifier(HiveParser_IdentifiersParser.java:10858)
	at org.apache.hadoop.hive.ql.parse.HiveParser.identifier(HiveParser.java:45918)
	at org.apache.hadoop.hive.ql.parse.HiveParser.columnName(HiveParser.java:36665)
	at org.apache.hadoop.hive.ql.parse.HiveParser.columnNameList(HiveParser.java:36528)
	at org.apache.hadoop.hive.ql.parse.HiveParser.insertClause(HiveParser.java:44680)
	at org.apache.hadoop.hive.ql.parse.HiveParser.regularBody(HiveParser.java:41270)
	at org.apache.hadoop.hive.ql.parse.HiveParser.queryStatementExpressionBody(HiveParser.java:40488)
	at org.apache.hadoop.hive.ql.parse.HiveParser.queryStatementExpression(HiveParser.java:40358)
	at org.apache.hadoop.hive.ql.parse.HiveParser.execStatement(HiveParser.java:1593)
	at org.apache.hadoop.hive.ql.parse.HiveParser.statement(HiveParser.java:1112)
	at org.apache.hadoop.hive.ql.parse.ParseDriver.parse(ParseDriver.java:202)
	at org.apache.hadoop.hive.ql.parse.ParseDriver.parse(ParseDriver.java:166)
	at org.apache.hadoop.hive.ql.Driver.compile(Driver.java:397)
	at org.apache.hadoop.hive.ql.Driver.compile(Driver.java:309)
	at org.apache.hadoop.hive.ql.Driver.compileInternal(Driver.java:1145)
	at org.apache.hadoop.hive.ql.Driver.runInternal(Driver.java:1193)
	at org.apache.hadoop.hive.ql.Driver.run(Driver.java:1082)
	at org.apache.hadoop.hive.ql.Driver.run(Driver.java:1072)
	at org.apache.hadoop.hive.cli.CliDriver.processLocalCmd(CliDriver.java:213)
	at org.apache.hadoop.hive.cli.CliDriver.processCmd(CliDriver.java:165)
	at org.apache.hadoop.hive.cli.CliDriver.processLine(CliDriver.java:376)
	at org.apache.hadoop.hive.cli.CliDriver.executeDriver(CliDriver.java:736)
	at org.apache.hadoop.hive.cli.CliDriver.run(CliDriver.java:681)
	at org.apache.hadoop.hive.cli.CliDriver.main(CliDriver.java:621)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.apache.hadoop.util.RunJar.run(RunJar.java:239)
	at org.apache.hadoop.util.RunJar.main(RunJar.java:153)
FAILED: ParseException line 1:29 cannot recognize input near '111' ',' ''ADIL'' in column name
hive> INSERT INTO TABLE STUDETAILS (111,'ADIL',87),(112,'BALA',76),(113,'CATHERIN',89),(114,'DAVID',66),(115,'EMILY',89),(116,'FARHAN',56),(117,'HARITHA',78);
NoViableAltException(302@[])
	at org.apache.hadoop.hive.ql.parse.HiveParser_IdentifiersParser.identifier(HiveParser_IdentifiersParser.java:10858)
	at org.apache.hadoop.hive.ql.parse.HiveParser.identifier(HiveParser.java:45918)
	at org.apache.hadoop.hive.ql.parse.HiveParser.columnName(HiveParser.java:36665)
	at org.apache.hadoop.hive.ql.parse.HiveParser.columnNameList(HiveParser.java:36528)
	at org.apache.hadoop.hive.ql.parse.HiveParser.insertClause(HiveParser.java:44680)
	at org.apache.hadoop.hive.ql.parse.HiveParser.regularBody(HiveParser.java:41270)
	at org.apache.hadoop.hive.ql.parse.HiveParser.queryStatementExpressionBody(HiveParser.java:40488)
	at org.apache.hadoop.hive.ql.parse.HiveParser.queryStatementExpression(HiveParser.java:40358)
	at org.apache.hadoop.hive.ql.parse.HiveParser.execStatement(HiveParser.java:1593)
	at org.apache.hadoop.hive.ql.parse.HiveParser.statement(HiveParser.java:1112)
	at org.apache.hadoop.hive.ql.parse.ParseDriver.parse(ParseDriver.java:202)
	at org.apache.hadoop.hive.ql.parse.ParseDriver.parse(ParseDriver.java:166)
	at org.apache.hadoop.hive.ql.Driver.compile(Driver.java:397)
	at org.apache.hadoop.hive.ql.Driver.compile(Driver.java:309)
	at org.apache.hadoop.hive.ql.Driver.compileInternal(Driver.java:1145)
	at org.apache.hadoop.hive.ql.Driver.runInternal(Driver.java:1193)
	at org.apache.hadoop.hive.ql.Driver.run(Driver.java:1082)
	at org.apache.hadoop.hive.ql.Driver.run(Driver.java:1072)
	at org.apache.hadoop.hive.cli.CliDriver.processLocalCmd(CliDriver.java:213)
	at org.apache.hadoop.hive.cli.CliDriver.processCmd(CliDriver.java:165)
	at org.apache.hadoop.hive.cli.CliDriver.processLine(CliDriver.java:376)
	at org.apache.hadoop.hive.cli.CliDriver.executeDriver(CliDriver.java:736)
	at org.apache.hadoop.hive.cli.CliDriver.run(CliDriver.java:681)
	at org.apache.hadoop.hive.cli.CliDriver.main(CliDriver.java:621)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.apache.hadoop.util.RunJar.run(RunJar.java:239)
	at org.apache.hadoop.util.RunJar.main(RunJar.java:153)
FAILED: ParseException line 1:30 cannot recognize input near '111' ',' ''ADIL'' in column name
hive> INSERT INTO TABLE STUDETAILS (111, 'ADIL' ,87),(112,'BALA',76),(113,'CATHERIN',89),(114,'DAVID',66),(115,'EMILY',89),(116,'FARHAN',56),(117,'HARITHA',78);
NoViableAltException(302@[])
	at org.apache.hadoop.hive.ql.parse.HiveParser_IdentifiersParser.identifier(HiveParser_IdentifiersParser.java:10858)
	at org.apache.hadoop.hive.ql.parse.HiveParser.identifier(HiveParser.java:45918)
	at org.apache.hadoop.hive.ql.parse.HiveParser.columnName(HiveParser.java:36665)
	at org.apache.hadoop.hive.ql.parse.HiveParser.columnNameList(HiveParser.java:36528)
	at org.apache.hadoop.hive.ql.parse.HiveParser.insertClause(HiveParser.java:44680)
	at org.apache.hadoop.hive.ql.parse.HiveParser.regularBody(HiveParser.java:41270)
	at org.apache.hadoop.hive.ql.parse.HiveParser.queryStatementExpressionBody(HiveParser.java:40488)
	at org.apache.hadoop.hive.ql.parse.HiveParser.queryStatementExpression(HiveParser.java:40358)
	at org.apache.hadoop.hive.ql.parse.HiveParser.execStatement(HiveParser.java:1593)
	at org.apache.hadoop.hive.ql.parse.HiveParser.statement(HiveParser.java:1112)
	at org.apache.hadoop.hive.ql.parse.ParseDriver.parse(ParseDriver.java:202)
	at org.apache.hadoop.hive.ql.parse.ParseDriver.parse(ParseDriver.java:166)
	at org.apache.hadoop.hive.ql.Driver.compile(Driver.java:397)
	at org.apache.hadoop.hive.ql.Driver.compile(Driver.java:309)
	at org.apache.hadoop.hive.ql.Driver.compileInternal(Driver.java:1145)
	at org.apache.hadoop.hive.ql.Driver.runInternal(Driver.java:1193)
	at org.apache.hadoop.hive.ql.Driver.run(Driver.java:1082)
	at org.apache.hadoop.hive.ql.Driver.run(Driver.java:1072)
	at org.apache.hadoop.hive.cli.CliDriver.processLocalCmd(CliDriver.java:213)
	at org.apache.hadoop.hive.cli.CliDriver.processCmd(CliDriver.java:165)
	at org.apache.hadoop.hive.cli.CliDriver.processLine(CliDriver.java:376)
	at org.apache.hadoop.hive.cli.CliDriver.executeDriver(CliDriver.java:736)
	at org.apache.hadoop.hive.cli.CliDriver.run(CliDriver.java:681)
	at org.apache.hadoop.hive.cli.CliDriver.main(CliDriver.java:621)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.apache.hadoop.util.RunJar.run(RunJar.java:239)
	at org.apache.hadoop.util.RunJar.main(RunJar.java:153)
FAILED: ParseException line 1:30 cannot recognize input near '111' ',' ''ADIL'' in column name
hive> INSERT INTO TABLE STUDETAILS VALUES(111,'ADIL',87),(112,'BALA',76),(113,'CATHERIN',89),
  (114,'DAVID',66),(115,'EMILY',89),(116,'FARHAN',56),(117,'HARITHA',78);
Query ID = bsac_20230412150923_44595732-6a91-45fb-ac3b-38f9d1d51347
Total jobs = 3
Launching Job 1 out of 3
Number of reduce tasks is set to 0 since there's no reduce operator
Starting Job = job_1681289940520_0001, Tracking URL = http://bsac-HP-280-Pro-G8-Microtower-PC:8088/proxy/application_1681289940520_0001/
Kill Command = /home/bsac/hadoop-2.9.1/bin/hadoop job  -kill job_1681289940520_0001
Hadoop job information for Stage-1: number of mappers: 1; number of reducers: 0
2023-04-12 15:09:31,313 Stage-1 map = 0%,  reduce = 0%
2023-04-12 15:09:35,439 Stage-1 map = 100%,  reduce = 0%, Cumulative CPU 1.78 sec
MapReduce Total cumulative CPU time: 1 seconds 780 msec
Ended Job = job_1681289940520_0001
Stage-4 is selected by condition resolver.
Stage-3 is filtered out by condition resolver.
Stage-5 is filtered out by condition resolver.
Moving data to: hdfs://localhost:50000/user/hive/warehouse/students.db/studetails/.hive-staging_hive_2023-04-12_15-09-23_510_1170615205335312394-1/-ext-10000
Loading data to table students.studetails
Table students.studetails stats: [numFiles=1, numRows=7, totalSize=95, rawDataSize=88]
MapReduce Jobs Launched: 
Stage-Stage-1: Map: 1   Cumulative CPU: 1.78 sec   HDFS Read: 3867 HDFS Write: 170 SUCCESS
Total MapReduce CPU Time Spent: 1 seconds 780 msec
OK
Time taken: 13.223 seconds
hive> SELECT * FROM STUDETAILS;
OK
111	ADIL	87
112	BALA	76
113	CATHERIN	89
114	DAVID	66
115	EMILY	89
116	FARHAN	56
117	HARITHA	78
Time taken: 0.14 seconds, Fetched: 7 row(s)
hive> LOAD DATA LOCAL INPATH '/home/bsac/studb.txt' TABLE STUDENTS;
FAILED: ParseException line 1:46 missing INTO at 'TABLE' near '<EOF>'
hive> LOAD DATA LOCAL INPATH '/home/bsac/studb.txt' INTO TABLE STUDENTS;
FAILED: SemanticException [Error 10001]: Line 1:57 Table not found 'STUDENTS'
hive> LOAD DATA LOCAL INPATH '/home/bsac/studb.txt' INTO TABLE STUDETAILS;
Loading data to table students.studetails
Table students.studetails stats: [numFiles=2, numRows=0, totalSize=174, rawDataSize=0]
OK
Time taken: 0.248 seconds
hive> nano studb.txt;
NoViableAltException(26@[])
	at org.apache.hadoop.hive.ql.parse.HiveParser.statement(HiveParser.java:1074)
	at org.apache.hadoop.hive.ql.parse.ParseDriver.parse(ParseDriver.java:202)
	at org.apache.hadoop.hive.ql.parse.ParseDriver.parse(ParseDriver.java:166)
	at org.apache.hadoop.hive.ql.Driver.compile(Driver.java:397)
	at org.apache.hadoop.hive.ql.Driver.compile(Driver.java:309)
	at org.apache.hadoop.hive.ql.Driver.compileInternal(Driver.java:1145)
	at org.apache.hadoop.hive.ql.Driver.runInternal(Driver.java:1193)
	at org.apache.hadoop.hive.ql.Driver.run(Driver.java:1082)
	at org.apache.hadoop.hive.ql.Driver.run(Driver.java:1072)
	at org.apache.hadoop.hive.cli.CliDriver.processLocalCmd(CliDriver.java:213)
	at org.apache.hadoop.hive.cli.CliDriver.processCmd(CliDriver.java:165)
	at org.apache.hadoop.hive.cli.CliDriver.processLine(CliDriver.java:376)
	at org.apache.hadoop.hive.cli.CliDriver.executeDriver(CliDriver.java:736)
	at org.apache.hadoop.hive.cli.CliDriver.run(CliDriver.java:681)
	at org.apache.hadoop.hive.cli.CliDriver.main(CliDriver.java:621)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.apache.hadoop.util.RunJar.run(RunJar.java:239)
	at org.apache.hadoop.util.RunJar.main(RunJar.java:153)
FAILED: ParseException line 1:0 cannot recognize input near 'nano' 'studb' '.'
hive> SELECT * FROM STUDETAILS;
OK
111	ADIL	87
112	BALA	76
113	CATHERIN	89
114	DAVID	66
115	EMILY	89
116	FARHAN	56
117	HARITHA	78
NULL	NULL	NULL
NULL	NULL	NULL
NULL	NULL	NULL
NULL	NULL	NULL
NULL	NULL	NULL
Time taken: 0.097 seconds, Fetched: 12 row(s)
hive> SELECT * FROM STUDETAILS;
OK
111	ADIL	87
112	BALA	76
113	CATHERIN	89
114	DAVID	66
115	EMILY	89
116	FARHAN	56
117	HARITHA	78
NULL	NULL	NULL
NULL	NULL	NULL
NULL	NULL	NULL
NULL	NULL	NULL
NULL	NULL	NULL
Time taken: 0.091 seconds, Fetched: 12 row(s)
hive> 

####################################6 a)
went to bin in hive folder and copied the bin file
bsau@bsau-V530-15ICB:~$ cd /home/bsau/apache-hive-3.1.2-bin/bin
bsau@bsau-V530-15ICB:~/apache-hive-3.1.2-bin/bin$ cd ..
bsau@bsau-V530-15ICB:~/apache-hive-3.1.2-bin$ mv metastore_db metastore_db.ymp (or) tmp
bsau@bsau-V530-15ICB:~/apache-hive-3.1.2-bin$ schematool -initSchema -dbType derby
SLF4J: Class path contains multiple SLF4J bindings.
SLF4J: Found binding in [jar:file:/home/bsau/Downloads/apache-hive-3.1.2-bin/lib/log4j-slf4j-impl-2.10.0.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: Found binding in [jar:file:/home/bsau/hadoop-2.9.1/share/hadoop/common/lib/slf4j-log4j12-1.7.25.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: See http://www.slf4j.org/codes.html#multiple_bindings for an explanation.
SLF4J: Actual binding is of type [org.apache.logging.slf4j.Log4jLoggerFactory]
Metastore connection URL:	 jdbc:derby:;databaseName=metastore_db;create=true
Metastore Connection Driver :	 org.apache.derby.jdbc.EmbeddedDriver
Metastore connection User:	 APP
Starting metastore schema initialization to 3.1.0
Initialization script hive-schema-3.1.0.derby.sql


  
bsau@bsau-V530-15ICB:~$ hive
create database hive;
use hive
create table Employee(
  in bigint,
  name string,
  age INT,
  salary bigint)