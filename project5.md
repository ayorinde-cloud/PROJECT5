# IMPLEMENTATION OF PROJECT5

## IMPLEMENTING A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS)

### STEP 1  - Create and configure two Linux-based virtual servers (EC2 instances in AWS)

![AWS EC2 Status](./images/EC2_INSTANCES_MYSQL-SERVER_AND_MYSQL-CLIENT.MPG)

### STEP 2 - On mysql server Linux Server install MySQL Server software.

`sudo apt update`

`sudo apt update`

`sudo apt install mysql server`

`sudo systemctl enable mysql`

`sudo sytstemctl status mysql`

![MYSQL-SERVER INSTALLED](./images/INSTALLING_MYSQL_SERVER.MPG)

### STEP 3 - On mysql client Linux Server install MySQL Client software.

`sudo apt install mysql-client`

![MYSQL-CLIENT INSTALLED](./images/INSTATLLING_MYSQL_CLIENT.MPG)

### STEP 4 – ON MYSQL SERVER LINUX SERVER ADD A NEW INBOUND RURE TO USE PORT 3306.

![PORT 3306](./images/ADDING_PORT_3306.MPG)

### STEP 5 - OPEN MYSQL-SERVER CONFIQ FILE AND REPLACE 127.0.0.1 IN THE “BINDING-ADDRESS”.

`sudo `vi /etc/mysql/mysql.conf.d/mysqld.cnf
          
![ BINDING ADDRESS STATUS](./images/BINDING_ADDRESS_0.0.0.0.MPG)

### STEP 6 - On mysql-client check the IP-address with the following code.

`curl http://checkip.amazonaws.com`

### STEP 7 On Mysql Server Linux Server security group inbound rule on port 3306 add mysql-client IP-address

![PORT 3306](./images/ADDING_PORT_3306_AND_MYSQL_CLIENT_IP.MPG)
      
### STEP 8 - On mysql-server create a new user @ mysql client IP-address.

`sudo mysql -p`
         
`Mysql > CREATE USER 'newuser2'@'13.53.217.137'.' IDENTIFIED BY 'password2';`
        
`Mysql > GRANT ALL PRIVILEGES ON * . * TO ‘newuser2@13.53.217.137’;`
    
![mysql server user](./images/newuser2_created_mysql_server.MPG)

### STEP 9 - On mysql-server check the IP-address with the following code

`curl http//checkip.amazonaws.com`

### STEP 10 - Connect to the Mysql-Server in Mysql-Client 

`mysql -u newuser2 -h 16.170.108.91 –p`

![mysql-client and mysql-server connection](./images/mysql_client_connecting_mysql_server.MPG)

`mysql > show database;`
        
![mysql Database](./images/MYSQL_SERVER_DATABASE.MPG)

