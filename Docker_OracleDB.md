# Setting up docker image on localhost for Oracle DB

1. Create an account on https://hub.docker.com/
2. Search for the docker image : Oracle Database Enterprise Edition
3. Login to docker on your mac.
```
$ docker login
```
4. Download the docker image.
```
docker pull store/oracle/database-enterprise:12.2.0.1
```
5. Start an instance of the db.
```
docker run -d -it --name MyOraDB -P store/oracle/database-enterprise:12.2.0.1
```
6. Check if the db is up. The status column against the started instance should show healthy.
```
docker ps
```
7. Check the port allocated by Docker for the db instance
```
docker port MyOraDB
```
Output would look like : 
```
1521/tcp -> 0.0.0.0:32769
```
8. Use the port shown (32769 in this case) in 7 to connect to the db.
You can download Oracle SQL Developer at https://www.oracle.com/technetwork/developer-tools/sql-developer/downloads/index.html
```
Username : sys
Password (default) : Oradoc_db1
Hostname : localhost
Port : 32769
ServiceName : ORCLCDB.localdomain
ConnectionType : Basic
Role : SYSDBA
```
