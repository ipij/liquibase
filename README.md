liquibase
=========

### Requirements

* Java 1.5
```
java -version
```

### Installation

1. Download Liquibase
```
wget http://sourceforge.net/projects/liquibase/files/Liquibase%20Core/liquibase-3.3.0-bin.zip/download -O liquibase-3.3.0-bin.zip
unzip liquibase-3.3.0-bin.zip
cd liquibase-3.3.0-bin.zip
```

2.Clone this repo
```
git clone git@github.com:ipij/liquibase.git ./
```

### Scenario by own

1. (branch step1) `cat liquibase.properties`
2. create `table1` table in PostgreSQL
3. `liquibase diff`
4. `liquibase diffChangeLog`
5. (branch step2) Create files as in step1 branch (such as master.xml)
6. `liquibase --changeLogFile=master.xml updateSQL`
7. `liquibase --changeLogFile=master.xml update`
8. `liquibase --changeLogFile=master.xml tag 1.0`
9. drop table1
10. (branch step3) `liquibase diffChangeLog`
11. (branch step4) `liquibase --changeLogFile=master.xml update`
12. `liquibase rollback 1.0`
