# Web Server (php + mysql + phpmyadmin)

## mysql  
mysql -u root -p
    
* __add user__
  1. create user 'user\_name'@'localhost' identified by 'password';  
    
* __grant privilages__
  1. grant all privileges on \*.\* to 'user\_name'@'localhost';
  2. grant all privileges on db\_name.\* to 'user'@'localhost';
    
* __delete user__
  1. drop user 'user\_name'@'localhost';
    
## errors
* __listen tcp 0.0.0.0:3306: bind: address already in use__
  1. sudo netstat -nlpt |grep 3306
  2. sudo service mysql stop (sudo service mysqld stop)
  3. sudo service apache2 stop
    
* __listen tcp 0.0.0.0:80: bind: address already in use__
  1. sudo nginx -s stop

* __cannot log in mysql__
  change user verification method to 5.0 version  
  1. docker exec -it 'db container name' /bin/bash
  2. mysql -u root -p
  3. ALTER USER 'user\_id' IDENTIFIED WITH mysql\_native\_password BY 'password';
