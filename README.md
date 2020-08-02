# sql_zhuanlan
包含四个数据库备份文件，分别为：

一、pg_test.sql 是使用pg_dump命令导出的postgresql的备份文件，下载后直接使用psql命令还原到本地数据库即可。  
步骤如下:    

1）创建test数据库：   
CREATE DATABASE "test"
WITH
  OWNER = "postgres"
  ENCODING = 'UTF8'
;   

2）使用命令还原：

psql -U postgres -f  pg_test.sql test  

二、mysql_test.sql   是使用mysqldump命令导出的MySQL备份文件，下载后使用以下方式恢复到本地数据库：  

1）连接到数据库并创建test数据库，使用以下命令切换到test库中  
      use test   
      
2） 使用以下命令还原 :  
   source mysql_test.sql  

三、SQLServer_test.bak 是通过SQLServer客户端工具 SQL Server Management Studio 导出的备份文件。

直接使用SQL Server Management Studio 即可恢复该备份文件。


四、oracle_test.dmp 是通过exp命令导出的Oracle备份文件，可以通过imp命令导入本地数据库   
例如：
imp system/password file=c:\oracle_test.dmp ignore=y FULL=Y
