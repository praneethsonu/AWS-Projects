# VPC Traffic Flow And Security

# AWS Networking Part - 2

# Architecture Diagram

<img width="1184" alt="architecture" src="https://github.com/user-attachments/assets/8c99ac18-2bc1-454f-a80e-96e0f6724bb6">

The core essentials of building an Amazon Virtual Private Cloud (VPC).

Let's get ready to:

1. 🚏 Create a route table.
2. 👮‍♀️ Create a security group.
3. 📋 Create a Network ACL (Network Access Control List).

# STEP #1

# Set up your VPC basics

![image](https://github.com/user-attachments/assets/c8a1a239-8cd0-4254-a03e-8b6a74948818)

# Create a VPC:

Off we go! Your VPC is the foundation for the rest of this project, and represents your corner of the AWS Cloud.

![image](https://github.com/user-attachments/assets/c6b9e43f-08c4-48d3-bb50-5d99dc0bd631)

4. Log in to your AWS Account - https://signin.aws.amazon.com/
5. In your AWS Management Console's search bar, search for VPC.
6. Select VPC from the drop-down menu.
7. In the left navigation pane, choose Your VPCs.
8. Make sure you're on the Region that's closest to you. Use the dropdown on the top right-hand corner to switch Regions.
9. Choose Create VPC.
10. Choose VPC Only.
11. Name tag: NextWork VPC 
12. IPv4 CIDR: 10.0.0.0/16
13. Select Create VPC.

# What is a CIDR block?

CIDR is a way to assign a whole block of IP addresses, kind of like creating a zone/area in a city.

To understand how big a CIDR block is, look at the number after the slash - the smaller the number, the larger the CIDR block!

![image](https://github.com/user-attachments/assets/903e4c6a-567a-472b-84c8-8e1807a9a1cc)

# Create Subnets:

![image](https://github.com/user-attachments/assets/b8bb218a-2b06-42cb-8391-33a91243d111)

14. In the VPC Dashboard, under Virtual Private Cloud, choose Subnets.
15. Choose Create subnet.
16. Configure your subnet settings:
     . VPC ID: NextWork VPC 
     . Subnet name: Public 1
     . Availability Zone: Select the first Availability Zone in the list.
     . IPv4 VPC CIDR block: 10.0.0.0/16
I    . IPv4 subnet CIDR block: 10.0.0.0/24
17. Choose Create subnet.
18. Select the checkbox next to Public 1.
19. In the Actions menu, select Edit subnet settings.
20. Check the box next to Enable auto-assign public IPv4 address.
21. Choose Save.

# Create an internet gateway:

Time to connect our VPC to the internet... with an internet gateway:

![image](https://github.com/user-attachments/assets/f9359817-22db-4c95-b1af-bb5c62d577bb)

22. In the left navigation pane, choose Internet gateways.
23. Choose Create Internet gateway.
24. Configure your internet gateway settings:
     Name tag: NextWork IG 
25. Choose Create Internet gateway.
26. Select your newly created internet gateway and choose Actions, then Attach to VPC.
27. Select NextWork VPC.
28. Select Attach internet gateway.

# STEP #2

# Create a route table

![image](https://github.com/user-attachments/assets/1237ffc3-8387-445f-ac45-edabe5a3d0fe)

29. In the left navigation pane, choose Route tables.
30. Refresh your page.
31. Ooo, two route tables! Why are there two?
32. Let's investigate. Select the checkbox for the first route table at the top of the list, then select the Routes tab.
33. Uncheck that route table, and switch to the bottom route table.
34. Select the Routes tab again.
35. Aha, the two tables have different routes!
36. Let's rename your NextWork VPC route table so it's easier to recognise.
37. Make sure you have your NextWork VPC route table selected - this is the route table with a single route to 10.0.0.0/16.
38. Select the pencil icon in the Name column of your route table.
39. Enter the name NextWork route table.
40. Select the Routes tab.
41. Choose Edit routes.
42. Choose Add route near the bottom of the page.
43. Destination:  0.0.0.0/0

![image](https://github.com/user-attachments/assets/98650076-5442-403b-9655-1b9952991fbb)

44. Target: Internet Gateway.
45. Select the only Internet Gateway ID option.
46. Choose Save Changes.
47. Choose the Subnet Associations tab.
48. Under the Explicit subnet associations tab, choose Edit subnet associations
49. Select  Public 1.
50. Choose Save associations.

# STEP #3

# Create a security group

![image](https://github.com/user-attachments/assets/05b6ef71-3aea-4d38-a09f-d1ae7fa13bab)

51. In the left navigation pane, choose Security Groups. Note that this is further down the navigation pane than our other pages so far!
52. Choose to Create a security group.
53. Security group name:  NextWork Security Group
54. Description: A Security Group for the NextWork VPC.
55. VPC: NextWork VPC
56. Under the Inbound rules panel, choose Add rule.
     Type: HTTP
     Source: Anywhere-IPv4
57. At the bottom of the screen, choose Create Security Group.

# STEP #4

# Create a Network ACL

To level up your VPC's security, let's add a network ACL i.e. network access control list.

![image](https://github.com/user-attachments/assets/b6446e15-7c5a-46cb-9fc2-96a6ebd571f1)

58. In the left navigation pane, choose Network ACLs.
59. Choose the network ACL that's associated with your Public 1 subnet, and check out the tabs for Inbound rules and Outbound rules.
![image](https://github.com/user-attachments/assets/0768238a-77fe-4359-bef4-8bba9f076396)

60. Select Create new network ACL.
61. Name: NextWork Network ACL
62. VPC: NextWork VPC
63. Select Create network ACL.
64. Select the checkbox next to your NextWork Network ACL
65. Select the Inbound rules tab.
66. Select Edit inbound rules.
67. Select Add new rule.
68. Rule number: 100.
69. Type: All traffic.
70. Source: 0.0.0.0/0
71. Click Save Changes.
72. Select the Outbound Rules tab.
73. Select Edit outbound rules.
74. Select Add new rule.
75. Rule number: 100
76. Type: All traffic.
77. Source: 0.0.0.0/0
78. Under the Subnet Associations tab, select Edit Subnet Associations.
79. Select your Public 1 subnet.
80. Select Save Changes.
81. Now check: do you have an Allow rule for both your inbound and outbound rules? Do you have a subnet association to Public 1?
82. Fantastic! You've done an incredible job setting up a functioning VPC.

Let's recap your VPC set up.

Here's what will happen if you were to set up an EC2 instance in your public subnet and host a web app there:

![image](https://github.com/user-attachments/assets/3dd6fd96-8f01-4769-b41e-2fb2c782d7c8)

# Delete Your All Resources.
