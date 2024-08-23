# Build a Virtual Private Cloud

The core of AWS networking by creating your very own Virtual Private Cloud (VPC).

Setting up and managing a VPC is a vital skill for anyone looking to master cloud infrastructure. Today, you'll learn how to set up and configure a VPC from scratch.

Let's get ready to:

1. ☁️ Create an Amazon VPC.
2. 🥅 Create a public subnet.
3. 🚪 Create an internet gateway.

# Architecture Diagram

![image](https://github.com/user-attachments/assets/e8c9c105-0d48-4d6b-a455-1e72e69c09dd)

# STEP #1

# Create a VPC

4. Off we go! Here's what we're creating in this step:

![image](https://github.com/user-attachments/assets/39333f06-36ee-4a6b-984c-a7b226a7344c)

5. In the AWS Management Console search field, type VPC.
6. Select VPC from the drop-down menu.

![Screenshot 2024-08-18 220402](https://github.com/user-attachments/assets/a862a3a3-2014-48b0-975c-55bdff927306)

7. In the left navigation pane, choose Your VPCs.
8. Make sure you're in the Region that's closest to you. Use the dropdown on the top right-hand corner to switch Regions.
9. You'll notice that there is already a VPC in your account!

![Screenshot 2024-08-18 220559](https://github.com/user-attachments/assets/62475df4-3397-4e8d-bef6-8216466a7805)

![image](https://github.com/user-attachments/assets/732c8d22-7a63-47d8-b623-4dcb75a27f1a)

10. Choose Create VPC.

![Screenshot 2024-08-18 222023](https://github.com/user-attachments/assets/22bf8ff2-1493-4cbe-b090-235823f73a82)

11. Choose VPC Only.
12. Name tag: NextWork VPC. 
13. IPv4 CIDR: 10.0.0.0/16.
14. Select Create VPC.

![Screenshot 2024-08-18 223521](https://github.com/user-attachments/assets/861cf975-fee7-4174-92d5-f011b3951a00)

![Screenshot 2024-08-18 223643](https://github.com/user-attachments/assets/718301ac-62fb-4208-a771-c30aacc01a7f)

# STEP #2

# Create Subnets

15. Nice! We've created our VPC, so it's time for the next step...creating a public subnet. Here's what it looks like in an architecture diagram:

![image](https://github.com/user-attachments/assets/42282c38-15e5-45a2-a52e-ae8c83688912)

16. Subnets are subdivisions within your VPC where you can launch AWS resources.
17. In the VPC Dashboard, under Virtual Private Cloud, choose Subnets.
18. Ooo, there are already subnets in here!

![Screenshot 2024-08-18 223745](https://github.com/user-attachments/assets/f91666c9-9ef0-4924-a0dd-c5a1b71176a1)

19. Choose Create subnet.

![Screenshot 2024-08-18 224333](https://github.com/user-attachments/assets/40e4cf7b-4164-4e8e-ac22-39f80117752e)

20. Configure your subnet settings:
     VPC ID: NextWork VPC.
     Subnet name: Public 1
     Availability Zone: Select the first Availability Zone in the list.
     IPv4 VPC CIDR block: 10.0.0.0/16
     IPv4 subnet CIDR block: 10.0.0.0/24

![Screenshot 2024-08-18 224739](https://github.com/user-attachments/assets/8a3f92a5-8ac5-4d3e-8ddf-1da0a12460bb)

![Screenshot 2024-08-18 224826](https://github.com/user-attachments/assets/463388ff-3691-44bc-aa9d-e8ccdcbe9fb1)

21. Choose Create subnet.

![image](https://github.com/user-attachments/assets/266cef6e-edba-4348-82da-4393f9618357)

22. Select the checkbox next to Public 1.
23. In the Actions menu, select Edit subnet settings.

![Screenshot 2024-08-18 224845](https://github.com/user-attachments/assets/aaa192b1-16e8-4fcd-998a-651d69583442)

24. Check the box next to Enable auto-assign public IPv4 address.

![Screenshot 2024-08-18 225003](https://github.com/user-attachments/assets/90cbb414-89e2-4ac9-aca8-7a7e95841d85)

25. Choose Save.

# STEP #3

# Create an internet gateway

26. VPC done!

27. Subnet done!

28. Time for the last step to connect our VPC to the internet... an Internet Gateway.
29. Here's what the architecture diagram looks like:

![image](https://github.com/user-attachments/assets/17e8b5c2-57f9-487c-8aa4-4e3273098d4a)

30. In the left navigation pane, choose Internet gateways.
