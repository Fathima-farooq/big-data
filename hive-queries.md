```bash
bsau@bsau-V530-15ICB:~/apache-hive-3.1.2-bin/bin$ cd .. bsau@bsau-V530-15ICB:~/apache-hive-3.1.2-bin$ mv metastore_db metastore_db.ymp
bsau@bsau-V530-15ICB:~/apache-hive-3.1.2-bin$ schematool -initSchema -dbType derbySLF4J:
Class path contains multiple SLF4J bindings. SLF4J: Found binding in [jar:file:/home/bsau/Downloads/apache-hive-3.1.2-bin/lib/log4j-slf4j-impl- 2.10.0.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: Found binding in [jar:file:/home/bsau/hadoop-2.9.1/share/hadoop/common/lib/slf4j-log4j12- 1.7.25.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: See http://www.slf4j.org/codes.html#multiple_bindings for an explanation. SLF4J: Actual binding is of type [org.apache.logging.slf4j.Log4jLoggerFactory]
Metastore connection URL: jdbc:derby:;databaseName=metastore_db;create=true
Metastore Connection Driver : org.apache.derby.jdbc.EmbeddedDriver
Metastore connection User: APP
Starting metastore schema initialization to 3.1.0
Initialization script hive-schema-3.1.0.derby.sql
Initialization script completed
schemaTool completed

opening hive:
bsau@bsau-V530-15ICB:~/apache-hive-3.1.2-bin$ hive
SLF4J: Class path contains multiple SLF4J bindings. SLF4J: Found binding in [jar:file:/home/bsau/Downloads/apache-hive-3.1.2-bin/lib/log4j-slf4j-impl- 2.10.0.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: Found binding in [jar:file:/home/bsau/hadoop-2.9.1/share/hadoop/common/lib/slf4j-log4j12- 1.7.25.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: See http://www.slf4j.org/codes.html#multiple_bindings for an explanation. SLF4J: Actual binding is of type [org.apache.logging.slf4j.Log4jLoggerFactory]
Hive Session ID = b4c02541-2ab8-48c2-bac6-2ac6d8542a95
Logging initialized using configuration in jar:file:/home/bsau/Downloads/apache-hive-3.1.2- bin/lib/hive-common-3.1.2.jar!/hive-log4j2.properties Async: true
Hive Session ID = e3e62f11-f71d-4277-8717-e30595954f0d
Hive-on-MR is deprecated in Hive 2 and may not be available in the future versions. Consider
using a different execution engine (i.e. spark, tez) or using Hive 1.X releases. hive

create database stu;
show databases;
use stu;
hive> CREATE TABLE STUDETAILS(SNO INT,SNAME STRING,SMARKS INT);
hive> SHOW TABLES;
hive> DESCRIBE STUDETAILS;
hive> INSERT INTO TABLE STUDETAILS VALUES(111,'ADIL',87),(112,'BALA',76),(113,'CATHERIN',89),
  (114,'DAVID',66),(115,'EMILY',89),(116,'FARHAN',56),(117,'HARITHA',78);
hive> SELECT * FROM STUDETAILS;

hive> LOAD DATA LOCAL INPATH '/home/bsac/studb.txt' INTO TABLE STUDETAILS;
hive> SELECT * FROM STUDETAILS;
```