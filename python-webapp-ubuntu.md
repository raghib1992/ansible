# Simple Web Application

This is a simple web application using [Python Flask](http://flask.pocoo.org/) and [MySQL](https://www.mysql.com/) database. 
This is used in the demonstration of development of Ansible Playbooks.
  
  Below are the steps required to get this working on a base linux system.
  
  - Install all required dependencies
  - Install and Configure Database
  - Start Database Service
  - Install and Configure Web Server
  - Start Web Server
******************************************************
# Ubuntu  
## 1. Install all required dependencies
  
  Python and its dependencies
```
sudo apt-get install software-properties-common
sudo apt-add-repository universe
sudo apt-get update
sudo apt-get install python-pip
sudo apt-get install -y python python-setuptools python-dev build-essential python-pip python-mysqldb
```
   
## 2. Install and Configure Database
    
 Install MySQL database
    
    apt-get install -y mysql-server mysql-client

## 3. Start Database Service
  - Start the database service
    
        service mysql start

  - Create database and database users
        
        # mysql -u <username> -p
        
        mysql> CREATE DATABASE employee_db;
        mysql> GRANT ALL ON *.* to db_user@'%' IDENTIFIED BY 'Passw0rd';
        mysql> USE employee_db;
        mysql> CREATE TABLE employees (name VARCHAR(20));
        
  - Insert some test data
        
        mysql> INSERT INTO employees VALUES ('JOHN');
    
## 4. Install and Configure Web Server

Install Python Flask dependency
```
pip install --upgrade setuptools
pip install --upgrade pip
pip install flask
pip install flask-mysql
```

- Copy app.py or download it from source repository
- Configure database credentials and parameters 

## 5. Start Web Server

Start web server
```
export FLASK_APP=app.py
flask run --host=0.0.0.0
```

## 6. Test

Open a browser and go to URL

    http://<IP>:5000                            => Welcome
    http://<IP>:5000/how%20are%20you            => I am good, how about you?
    http://<IP>:5000/read%20from%20database     => JOHN
**************************************************
# Centos
WebApp Installation Instructions on Centos 7
WebApp  Installation Instructions for Centos 7


The installation procedure is a bit different on Centos 7. So those of you following this course from the first course, please follow the below instructions:

# Install Python Pip and dependencies on Centos 7

-------------------------------------------------

sudo yum install -y epel-release python python-pip

sudo pip install flask flask-mysql

# If you come across a certification validation error while running the above command, please use the below command.

# sudo pip install --trusted-host files.pythonhosted.org --trusted-host pypi.org --trusted-host pypi.python.org flask flask-mysql



# Install MySQL Server on Centos 7

---------------------------------------------
```

wget http://repo.mysql.com/mysql-community-release-el7-5.noarch.rpm

sudo rpm -ivh mysql-community-release-el7-5.noarch.rpm

sudo yum update

sudo yum -y install mysql-server

sudo service mysql start
```

The complete playbook to get the same workin on CentOS is here:

https://github.com/kodekloudhub/simple_web_application
**********************************************