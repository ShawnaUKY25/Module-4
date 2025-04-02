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

**Command:**  
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

**Command:**  
```sh
sudo apt install php libapache2-mod-php
```

**Configuration Changes:**  
- Updated Apache settings to prioritize `index.php` over `index.html`.  
- Created an `info.php` file to test PHP functionality.  

**Verification:**  
- Confirmed PHP installation using:  
  ```sh
  php -v
  ```
- Verified the `info.php` page loaded correctly in the browser.  

**Challenges & Solutions:**  
- Process was easier than Apache2 installation.  
- Learned to be more detail-oriented after prior `Nano` saving issues.  

---

### 3. Installing MySQL  

**Commands:**  
```sh
sudo apt install mysql-server
```

Configured security settings using:  
```sh
sudo mysql_secure_installation
```

**Configuration Changes:**  
- Created a new MySQL database.  
- Added a table for a book catalog with relevant columns.  
- Assigned user permissions using PHP scripts.  

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
