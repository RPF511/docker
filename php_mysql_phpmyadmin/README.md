# Web Server (php + mysql + phpmyadmin)

## mysql  
    mysql -u root -p
    
    * add user
      1. create user 'user\_name'@'localhost' identified by 'password';  
    
    * grant privilages
      1. grant all privileges on \*.\* to 'user\_name'@'localhost';
      2. grant all privileges on db\_name.\* to 'user'@'localhost';
    
    * delete user
      1. drop user 'user\_name'@'localhost';
    
## errors
    * listen tcp 0.0.0.0:3306: bind: address already in use
      1. sudo netstat -nlpt |grep 3306
      2. sudo service mysql stop (sudo service mysqld stop)
      3. sudo service apache2 stop
    
    * listen tcp 0.0.0.0:80: bind: address already in use
      1. sudo nginx -s stop

    * cannot log in mysql  
      change user verification method to 5.0 version  
      1. docker exec -it 'db container name' /bin/bash
      2. mysql -u root -p
      3. ALTER USER 'user\_id' IDENTIFIED WITH mysql\_native\_password BY 'password';

