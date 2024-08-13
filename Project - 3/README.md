# Cloud Security with AWS IAM
Let's use IAM to control access to our AWS resources.

# Introduction to the project.

In AWS, a user is a person or a computer that can do things on the AWS cloud.

You use AWS Identity and Access Management (IAM) to control who is authenticated (signed in) and authorized (has permissions) to use your account's resources.

Get ready to create (Tools):

1. 💻 EC2 instances
2. 📏 IAM Policies
3. 👩‍👩‍👧‍👧 IAM Users and User Groups
4. 🔖 AWS Account Alias

# Architecture Diagram

<img width="645" alt="architecture" src="https://github.com/user-attachments/assets/44f4aaac-47d4-4e48-8f2a-76e48411e97e">

# About Project
Welcome to the NextWork team! You've just joined our dynamic team as a DevOps engineer, and we're thrilled to have you on board. 👋

Boost our computing power to match increased traffic to the website. Lots of new students want to learn with NextWork over the break!
Onboard an intern that's working at NextWork - you're asked to make sure they have the right permission settings to contribute while keeping the company's resources secure.

# STEP #1

# Launch EC2 Instances with Tags

1. Log in to your https://console.aws.amazon.com/
![Screenshot 2024-08-13 200412](https://github.com/user-attachments/assets/06e25844-7725-4a99-a29c-aa9d986a6fa4)
  
2. Head to EC2
![Screenshot 2024-08-13 200439](https://github.com/user-attachments/assets/fe259a47-76e4-42d7-b8ce-9c2df2d65be2)
 
3. Switch your Region to the one closest to you!
4. In your EC2 console, choose Launch Instances
5. Let's set up your EC2 instance!
6. In Name, enter the value nextwork-production-yourname. Yup, replace yourname with your name.
7. Choose Add additional tags, which is right next to your Name field.
![Screenshot 2024-08-13 200627](https://github.com/user-attachments/assets/3e614b97-25b8-4638-a763-fe09fa769e69)

8. Choose Add new tag.
9. For the next tag, use this information:
      Key: Env
      Value: production
![Screenshot 2024-08-13 200815](https://github.com/user-attachments/assets/e46a69dd-acd3-406c-b362-e4d309816920)

10. Head on down to see your EC2 settings and make sure the Amazon Machine Image (AMI) is using a Free tier eligible option.
![Screenshot 2024-08-13 200905](https://github.com/user-attachments/assets/289aef8f-af79-4372-aed7-4340d34c4ed2)

11. For the instance type, also make sure you're using a Free tier eligible option!
![Screenshot 2024-08-13 201503](https://github.com/user-attachments/assets/f15a8dfa-c566-4294-ba28-42c930cbc409)

12. For Key pair (login), select Proceed without a key pair.
![Screenshot 2024-08-13 201527](https://github.com/user-attachments/assets/250fcc4f-aee9-48e3-835a-fb1992de35ab)

13. You're ready! Click Launch instance.
![Screenshot 2024-08-13 201557](https://github.com/user-attachments/assets/d830da37-fd0c-4325-94fe-a3d2c0c2af48)

![Screenshot 2024-08-13 201607](https://github.com/user-attachments/assets/6594ec07-dc1d-4804-8c16-3fc16ccecd93)

![Screenshot 2024-08-13 201651](https://github.com/user-attachments/assets/95706ff1-4090-4f9e-a3b0-7999bcb94688)

14. Now let's create one more EC2 instance for the development environment.
15. Repeat the same flow, but this time using these tags:
      Name: nextwork-development-yourname
      Env: development
16. Launch your second instance.
17. Select from your left hand navigation panel.
18. If you only see one instance on your page, make sure to use that refresh button!
19. Let's have a look at your wonderful work.
20. Select the checkbox next to one of your instances, and a popup window of information pops up!
21. Select the Tags tab.
![Screenshot 2024-08-13 202931](https://github.com/user-attachments/assets/0e5ff4f2-a781-44d0-aba9-69666537aaaa)
22. you'll see the tags you've defined right here.

![Screenshot 2024-08-13 203038](https://github.com/user-attachments/assets/342422bc-5295-46b4-8071-5462a3defe75)

23. You've just deployed two EC2 instances (servers) with different tag values.

