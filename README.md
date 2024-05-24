# Create and Host a Wordpress Website on AWS EC2

Step 1: Launch an instance
AMI — Ubuntu Server
Instance Type — t2.micro
Key Pair — ppk file format
Firewall (security groups) — ssh, http, https
Configuration Storage — 8 GB, gp2
No. of Instance — 01

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
![Screenshot 2024-05-24 172954](https://github.com/praneethsonu/AWS-Projects/assets/166925251/ab35d3df-4714-470c-89eb-1d650bed744b)
![Screenshot 2024-05-24 173027](https://github.com/praneethsonu/AWS-Projects/assets/166925251/99e88e55-1cd9-4577-83fb-08dcb296abfd)
To Install Apache server on Ubuntu
```bash
sudo apt install apache2
```
![Screenshot 2024-05-24 173121](https://github.com/praneethsonu/AWS-Projects/assets/166925251/4f6895b2-cacf-40d7-92a3-77a893f1af94)








