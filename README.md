# Workspace configuration

### 1. GIT
First, we need to download and install git. Git installation is different on all operating systems, so please refer to this link: [https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
During installation pay attention to default text editor - you may want to choose VSCode, Nano, Notepad++, or anything other than vim :)
Then, remember to set up your git: [https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)
The most important variables to change are:
```sh
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```
Now, we can test if Git works OK. Create a folder on your desktop, or your documents, where you will store all your project files. Now, enter this folder and use this command:
```sh
git clone https://github.com/kamdz01/voting_app.git
```
If there are no errors, you should be ready to use Git.

### 2. Docker
Now, we need to download and install Docker and Docker Compose. The easiest way is to install Docker Desktop form here: [https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop)
Docker Desktop contains docker, docker deamon, docker compose, and some more functionalities we won't use.

When we have installed and ready Docker Desktop, we launch it.

Now, we have to download setup files, for our docker. Head up to your project folder and use this command:
```sh
git clone https://github.com/harshalone/docker-compose-lamp.git
```
then, enter newly downloaded folder:
```sh
cd docker-compose-lamp
```
Now we have to create config file for our docker. Let's copy sample one:
```sh
cp sample.env .env
```
We have created our config file, now let's edit it. You can use any tet editor for it.
```sh
# Please Note:
# In PHP Versions <= 7.4 MySQL8 is not supported due to lacking pdo support

# To determine the name of your containers
COMPOSE_PROJECT_NAME=lamp

# Possible values: php54, php56, php71, php72, php73, php74
PHPVERSION=php74
DOCUMENT_ROOT=./www
VHOSTS_DIR=./config/vhosts
APACHE_LOG_DIR=./logs/apache2
PHP_INI=./config/php/php.ini

# Possible values: mariadb, mysql, mysql8
DATABASE=mysql
MYSQL_DATA_DIR=./data/mysql
MYSQL_LOG_DIR=./logs/mysql

# If you already have the port 80 in use, you can change it (for example if you have Apache)
HOST_MACHINE_UNSECURE_HOST_PORT=80
HOST_MACHINE_SECURE_HOST_PORT=443

# If you already have the port 3306 in use, you can change it (for example if you have MySQL)
HOST_MACHINE_MYSQL_PORT=3306

# If you already have the port 8080 in use, you can change it
HOST_MACHINE_PMA_PORT=8080

# If you already has the port 6379 in use, you can change it (for example if you have Redis)
HOST_MACHINE_REDIS_PORT=6379

# MySQL root user password
MYSQL_ROOT_PASSWORD=tiger

# Database settings: Username, password and database name
MYSQL_USER=docker
MYSQL_PASSWORD=docker
MYSQL_DATABASE=docker
```

You should change:
- DATABASE from mysql to mariadb
- DOCUMENT_ROOT to our github repo, that we have downloaded in 1 point.
- MYSQL_DATA_DIR to DOCUMENT_ROOT/data/mysql
- MYSQL_LOG_DIR to DOCUMENT_ROOT/logs/mysql

Now we have all configs ready and can head up to building docker containers. We will use simple command for this:
```sh
docker-compose up
```
If this command does not work, you may want to change General/Use Docker Compose V2 to off in Docker Desktop settings.
Now it should work without any problems.

### 3.Our workspace

After our docker containers are downloaded and ran, we can head up to localhost in our browser. We should now be able to see our website there.
If you want to use PhpMyAdmin, head up to localhost:8080

If you want to develop and edit our project, you should open our git repository in your favourite code editor (I suggest using Visual Studio Code, because it works well with git)





