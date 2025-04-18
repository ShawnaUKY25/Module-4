# Module-4

## Introduction

A **LAMP stack** is a popular open-source software bundle used to build and run websites and web applications. It consists of:

- **Linux**: Operating system  
- **Apache**: Web server  
- **MySQL**: Database  
- **PHP**: Programming language  

Libraries and businesses commonly use the LAMP stack because it is **free, flexible, and reliable**, making it ideal for hosting digital repositories, managing content, and running applications like **integrated library systems (ILS)** and **content management systems (CMS)**.

---

## Installation and Configuration

### 1. Installing Apache2  
**Start Up/Update**

- Install and update apps and operating system

**Installation Command:**  
```sh
sudo apt install apache2
```

**Configuration Changes:**  
- Switched out the default `index.html` webpage.  
- Used `Nano` to edit the default Apache webpage.  

**Verification:**  
- Saved and confirmed the new index page text.  
- Verified the file is correctly placed in `/var/www/html/`.  
- Loaded the modified `index.html` in a browser to ensure it displayed correctly.  

**Challenges & Solutions:**  
- Initially struggled with saving in `Nano` (resolved with `Ctrl + O`, then `Ctrl + X`).  
- Mistyped filenames multiple times, requiring corrections and verification.  

---

### 2. Installing PHP  

**Start Up/Update**

- Install and update apps and operating system

**Command:**  

```sh
sudo apt install php libapache2-mod-php
sudo systemctl restart apache2
```

- Confirmed PHP installation using:  
```sh
php -v
```

- Check status after reboot
```sh
systemctl status apache2
```
- Set New defaults to index.php vs.index.html
```sh
  cd /etc/apache2/mods-enabled/
  sudo cp dir.conf dir.conf.bak
  sudo nano dir.conf
```

**Check Installation:**
```sh
cd /var/www/html/
sudo nano info.php
```

**Configuration Changes:**  
- Updated Apache settings to prioritize `index.php` over `index.html`.  
- Test to confirm php configuration change.  
```sh
apachectl configtest
```
**Verification:** 

- Verified the `info.php` page loaded correctly in the browser using this url.
  
  http://34.29.1.232/index.php

**Challenges & Solutions:**  
- Process was easier than Apache2 installation.  
- Learned to be more detail-oriented after prior `Nano` saving issues.  

---

### 3. Installing MySQL  

**Start Up/Update**

- Install and update apps and operating system

**Commands:**  
```sh
sudo apt install mysql-server
```

Configured security settings using:  
```sh
sudo mysql_secure_installation
```

**Configuration Changes:**  
- Changed the configuration.
```sh
Validate passwords: Y
Password validation policy: 0 (zero) for LOW
Remove anonymous users: Y
Disallow root login remotely: Y
Remove test database and access to it: Y
Reload privilege tables now: Y
```
- Loggedin to SQL
```sh
sudo mysql -u root
```
-Searched for SQL Databases
```sh
mysql> show databases;
```
- Created a New Database called opacdb
```sh
mysql> create database opacdb default character set utf8mb4 collate utf8mb4_unicode_ci;
mysql> show databases;
mysql> grant all privileges on opacdb.* to 'opacuser'@'localhost' with grant option;
```
- Created a table in SQL
```sh
mysql> show databases;
mysql> use opacdb;
```
- Set up the perameters for the identifyers for a book catalog with relevant columns.
```sh
mysql> create table books (
id int unsigned not null auto_increment,
author varchar(150) not null,
title varchar(150) not null,
copyright year(4) not null,
primary key (ID) );
```
- Include additonal book data to the tables
```sh
 cd /var/www
 sudo touch login.php
 sudo chmod 640 login.php
 sudo chown :www-data login.php
 ls -l login.php
 sudo nano login.php
```
- Assigned user login permissions using PHP scripts.  
```sh
  <?php // login.php
  $db_hostname = "localhost";
  $db_database = "opacdb";
  $db_username = "replace with ourt SQL user";
  $db_password = "replace with thw SQL user's pw"; ?>
```
**Verification:**  
- Successfully ran queries to **view, update, insert, and delete** records.  
- Connected MySQL and PHP, enabling dynamic data retrieval.  

**Challenges & Solutions:**  
- Mistyped PHP scripts a few times, requiring multiple corrections.  
- Tired eyes led to input errors toward the end of the process.  

---

## Site Links

- **Index.php page on Ubuntu server**: [http://34.29.1.232/index.php](http://34.29.1.232/index.php)  
- **opac.php page on Ubuntu server**: [http://34.29.1.232/opac.php](http://34.29.1.232/opac.php)  
