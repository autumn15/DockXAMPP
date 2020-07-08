# DockXAMPP
 This is a XAMPP-like environment that can be built by docker-compose.
 Tested on Ubuntu 18.04.

## Set up
### 1. Install docker and docker-compose
- docker: https://docs.docker.com/engine/install/ubuntu/
- docker-compose: https://docs.docker.com/compose/install/


### 2. Start Docker service
Start docker service.

```
$ sudo service docker start
```

### 3. Build 
Execute the following command in the directory where `docker-compose.yml` is located.

```
$ docker-compose build
```

### 4. Create your files

Place your files on `htdocs`. 

※ When using Database in your PHP program, describe as follows.

```php

........
$dsn = 'mysql:dbname='.$DBNAME.';host=mysql-container;charset=utf-8';
$user = 'root';
$password = 'password';
$dbh = new PDO($dsn, $user, $password);
$dbh->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
........

```


## Start

```
$ docker-compose up -d
```

To access phpMyAdmin, go to `http://localhost:8080` on your browser.

## Stop

```
$ docker-compose down
```
