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

28. Time for the last step to connect our VPC to the Internet... an Internet Gateway.
29. Here's what the architecture diagram looks like:

![image](https://github.com/user-attachments/assets/17e8b5c2-57f9-487c-8aa4-4e3273098d4a)

30. In the left navigation pane, choose Internet gateways.
31. Aha! An existing internet gateway.
![Screenshot 2024-08-18 225728](https://github.com/user-attachments/assets/d7354feb-f21e-4700-ba04-103fc0fd8055)
32. Choose Create Internet gateway.
33. Configure your internet gateway settings:
     Name tag: NextWork IG.
     Choose Create Internet Gateway.
    
![Screenshot 2024-08-18 225753](https://github.com/user-attachments/assets/ee2248d0-6e69-4106-b6b2-e5a7e4424fec)

35. Select your newly created internet gateway and choose Actions, then Attach to VPC.

![Screenshot 2024-08-18 225841](https://github.com/user-attachments/assets/342f2576-d52d-4554-a129-b30319a67cc4)

36. Select NextWork VPC.
37. Select Attach internet gateway.

38. Even though you've created an Internet Gateway and attached it to your VPC, there's still a step left to go... you still have to tell instances in your public subnet how to get to the internet. This involves setting up route tables to direct traffic from your instances to your internet gateway!

39. We'll jump into that in the next project... but in the meantime, that's a WRAP for the very first AWS networking project! Well done 👏

40. Completed today's project and set up your very own virtual private cloud with Amazon VPC.

# STEP #4

# Delete Your Resources

41. Before you read the steps on deleting your resources, do you think you can challenge yourself to try delete everything in this project without any guidance?

42. Keeping track of your resources, and deleting them at the end, is absolutely a skill that will help you reduce waste in your account.

VPC:

. In your VPC console, select the checkbox next to NextWork VPC.
. Select the Actions dropdown.
. Select Delete VPC.
   . Note down the VPC ID of the VPC you are deleting - you might need this when deleting the other resources!

43. Your subnet and internet gateway should be deleted automatically with your VPC, but it's a good idea to check this anyway.
![image](https://github.com/user-attachments/assets/a610938f-9f18-4e21-9c85-e35960b8c72d)

44. Your subnet and internet gateway should be deleted automatically with your VPC, but it's a good idea to check this anyway.
