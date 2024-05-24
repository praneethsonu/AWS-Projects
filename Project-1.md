# Create And Host A WordPress Website On AWS EC2

![Create and Host a Wordpress Website on AWS EC2 with your own domain name](https://github.com/praneethsonu/AWS-Projects/assets/166925251/cacc261f-8b51-4b59-a20b-b9db9438557f)

Step 1: 
1. Launch an instance
2. AMI — Ubuntu Server
3. Instance Type — t2.micro
4. Key Pair — ppk file format
5. Firewall (security groups) — SSH, HTTP, HTTPS
6. Configuration Storage — 8 GB, gp2
7. No. of Instance — 01

→ Launch Instance
![18](https://github.com/praneethsonu/AWS-Projects/assets/166925251/0a20c58d-ad58-4f14-941b-a9c9781aff7b)

Step 2: Elastic IP address
![20](https://github.com/praneethsonu/AWS-Projects/assets/166925251/6b3bd40a-a015-4218-93c4-bc48a41295cd)

In Action Select Associate Elastic IP address
![24](https://github.com/praneethsonu/AWS-Projects/assets/166925251/23e6a2db-a7a4-4e4b-a444-76dd80fb43f1)
![26](https://github.com/praneethsonu/AWS-Projects/assets/166925251/a362930b-0548-444c-9795-2a656128809e)
![27](https://github.com/praneethsonu/AWS-Projects/assets/166925251/0793e5e3-d257-42a8-bb25-28b3b08aa1a8)

Step 3: Connect via SSH Client(MobaXterm)
![Screenshot 2024-05-24 170430](https://github.com/praneethsonu/AWS-Projects/assets/166925251/18e6d514-dae4-4ce1-a8f5-095051ab1406) 

Connect by SSH session
![Screenshot 2024-05-24 172331](https://github.com/praneethsonu/AWS-Projects/assets/166925251/720bf9b7-99a9-4a63-a9bd-69afba8d5743)

I have connected to a virtual computer…
![Screenshot 2024-05-24 172954](https://github.com/praneethsonu/AWS-Projects/assets/166925251/ab35d3df-4714-470c-89eb-1d650bed744b)
![Screenshot 2024-05-24 173027](https://github.com/praneethsonu/AWS-Projects/assets/166925251/99e88e55-1cd9-4577-83fb-08dcb296abfd)

Step 4: Installing and Configuring MySQL server:
To Install Apache server on Ubuntu
```bash
sudo apt install apache2
```
![Screenshot 2024-05-24 173121](https://github.com/praneethsonu/AWS-Projects/assets/166925251/4f6895b2-cacf-40d7-92a3-77a893f1af94)
Copy Publoc IP into the new tap in the browser
![Screenshot 2024-05-24 174504](https://github.com/praneethsonu/AWS-Projects/assets/166925251/2a4c1a5e-e3e3-452c-bcf4-a696fbbf0f4c)

Install PHP runtime because WordPress build on PHP
```bash
sudo apt install php libapache2-mod-php php-mysql
```
![Screenshot 2024-05-24 174808](https://github.com/praneethsonu/AWS-Projects/assets/166925251/055ddc20-b055-4304-8a33-2456ab8f4ed9)

1. Install MySQL server
```bash   
sudo apt install mysql-server
```
![Screenshot 2024-05-24 174856](https://github.com/praneethsonu/AWS-Projects/assets/166925251/a9c740b6-652f-455e-b88e-544f4fffcfb5)
 

2. Login to MySQL server
```bash
sudo mysql -u root
```
![Screenshot 2024-05-24 175008](https://github.com/praneethsonu/AWS-Projects/assets/166925251/d0ba5a06-2323-442c-9582-8af872d3fda7)


3. Change the authentication plugin to mysql_native_password (change the password to something strong)
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password by 'Testpassword@123';

4. Create a new database user for WordPress (change the password to something strong)
CREATE USER 'wp_user'@localhost IDENTIFIED BY 'Testpassword@123';

5. Create a database for WordPress
CREATE DATABASE wp;

6. Grant all privileges on the database 'wp' to the newly created user
GRANT ALL PRIVILEGES ON wp.* TO 'wp_user'@localhost;
Exit or ctrl-D
![Screenshot 2024-05-24 175459](https://github.com/praneethsonu/AWS-Projects/assets/166925251/1142af6a-07ed-422c-98ab-0fae60ec1768)

Step 5: Download, Configure & Install WordPress:

Download WordPress
```bash
cd /tmp
wget https://wordpress.org/latest.tar.gz
```
Unzip 
```bash
tar -xvf latest.tar.gz
```
![Screenshot 2024-05-24 180057](https://github.com/praneethsonu/AWS-Projects/assets/166925251/8ffab688-4bf1-4054-8389-329ca9ffe2ad)

Move WordPress folder to Apache document root
```bash
sudo mv wordpress/ /var/www/html
```
![Screenshot 2024-05-24 180337](https://github.com/praneethsonu/AWS-Projects/assets/166925251/1d903d50-85b3-4e53-98a9-41a5484cf9ab)
![Screenshot 2024-05-24 180651](https://github.com/praneethsonu/AWS-Projects/assets/166925251/724d6b7f-e76d-40f1-98b6-5d48ad63faf6)
![Screenshot 2024-05-24 180839](https://github.com/praneethsonu/AWS-Projects/assets/166925251/df413759-387a-4310-8e6d-5fdc633b3480)

It threw an error, doesn't matter copy the Configuration rules. create the wp-config.php file manually and paste the following text into it.
```bash
cd /var/www/html/wordpress
vi wp-config.php
```
![image](https://github.com/praneethsonu/AWS-Projects/assets/166925251/9f57ab62-ef38-4b8a-b252-25f53371630b)
![Screenshot 2024-05-24 181633](https://github.com/praneethsonu/AWS-Projects/assets/166925251/ebf88656-7b40-46de-9fe8-954065e5859e)
Try to open with your address followed by WordPress
3.215.11.193/WordPress/
![Screenshot 2024-05-24 181905](https://github.com/praneethsonu/AWS-Projects/assets/166925251/ad94ec2f-bfd7-44ea-8fb9-6ad4f500d0a5)
![Screenshot 2024-05-24 181941](https://github.com/praneethsonu/AWS-Projects/assets/166925251/e51da7a5-fc12-42a4-9508-b1828a4f3055)

I don't want my website to go to the subpath (3.215.11.193/WordPress) like this. I want it to serve on the root directory like this (3.215.11.193), as of now root directory serves the Apache root default page, but I want the WordPress website to the server at this root path. for that, I need to modify the Apache configuration, so I go back to my terminal rest follow the below commands.
```bash
cd /etc/apache2/sites-available/
vi 000-default.conf
```
![Screenshot 2024-05-24 182220](https://github.com/praneethsonu/AWS-Projects/assets/166925251/7064db23-871f-410f-8198-d118aa0b2edd)

Change document root to /var/www/html/wordpress
```bash
sudo systemctl restart apache2
```
![Screenshot 2024-05-24 183023](https://github.com/praneethsonu/AWS-Projects/assets/166925251/c7f7f80d-e163-4c14-98a4-c15f7b3d19bf)
![Screenshot 2024-05-24 183116](https://github.com/praneethsonu/AWS-Projects/assets/166925251/2af433de-2d71-4a1c-a208-1b35afd4ef03)
http://3.215.11.193/ # hit on browser
![Screenshot 2024-05-24 183146](https://github.com/praneethsonu/AWS-Projects/assets/166925251/5da0bc56-0357-4048-b3d4-9cfa372c3344)

WordPress website is created & hosted


















