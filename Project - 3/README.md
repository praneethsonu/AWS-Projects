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
![Screenshot 2024-08-13 203038](https://github.com/user-attachments/assets/342422bc-5295-46b4-8071-5462a3defe75)
21. Select the Tags tab.
23. you'll see the tags you've defined right here.
![Screenshot 2024-08-13 202931](https://github.com/user-attachments/assets/0e5ff4f2-a781-44d0-aba9-69666537aaaa)
24. You've just deployed two EC2 instances (servers) with different tag values.

# STEP #2

# Create an IAM Policy

25. Head to your IAM Console.
![Screenshot 2024-08-13 203059](https://github.com/user-attachments/assets/13544761-3065-4056-b27b-396ec95674b6)

26. Now on the left-hand navigation panel of your IAM console, choose Policies.
![Screenshot 2024-08-13 203219](https://github.com/user-attachments/assets/ffc8b36f-9974-4454-84c6-5169312b0c85)

27. Choose Create Policy.
28. Switch your Policy editor tab to JSON.
![Screenshot 2024-08-13 203332](https://github.com/user-attachments/assets/14cc419f-cb8e-4006-a9ba-7dd0f39151fb)

29. Here's the policy you'll be using! Paste this policy into your editor - replace ALL of the existing code in your editor.

# CODE

{    
  "Version": "2012-10-17",    
  "Statement": [        
    {            
      "Effect": "Allow",            
      "Action": "ec2:*",            
      "Resource": "*",            
      "Condition": {                
        "StringEquals": {                    
          "ec2:ResourceTag/Env": "development"                
        }            
      }        
    },        
    {            
      "Effect": "Allow",            
      "Action": "ec2:Describe*",            
      "Resource": "*"        
    },        
    {            
      "Effect": "Deny",            
      "Action": [                
        "ec2:DeleteTags",                
        "ec2:CreateTags"            
      ],            
      "Resource": "*"        
    }    
  ] 
}

30. Select Next when you're ready.
31. Fill in your policy's details:
    Name: NextWorkDevEnvironmentPolicy 
    Description: IAM Policy for NextWork's development environment.
32. Choose Create policy. 
33. Oh no! Turns out there's a rule for the characters allowed in your Policy description. Edit this description to get rid of that error (can you tell which character is not valid? There's a hint given to you right underneath the Description's text box)!
34. Choose Create policy again when you're done.
![Screenshot 2024-08-13 204620](https://github.com/user-attachments/assets/bfc306eb-f468-449e-b4b5-eae98fe16715)

# STEP #3

# Create an AWS Account Alias

35. Head to your IAM dashboard.
36. In the right-hand side of the dashboard, choose Create under Account Alias.
![Screenshot 2024-08-13 205036](https://github.com/user-attachments/assets/a4eb9535-029d-4072-bb6a-4775202bc4cc)

37. In the Preferred alias field, enter nextwork-alias-yourname. Yup, replace yourname with your name!
![Screenshot 2024-08-13 205137](https://github.com/user-attachments/assets/00322e1e-7214-438e-815d-6141c1eaf891)

38. Choose Create alias.

# STEP #4

# Create IAM Users and User Groups

39. Choose User groups in your left-hand navigation panel.
40. Choose Create group.
41. Let's create your first user group!
42. To set up your user group:
    Name: nextwork-dev-group
    Attach permission policies: NextWorkDevEnvironmentPolicy
![Screenshot 2024-08-13 205827](https://github.com/user-attachments/assets/1f03618f-5a20-4b79-98ae-ab53f5e24f7e)

43. Select Create user group. Success!
![Screenshot 2024-08-13 205852](https://github.com/user-attachments/assets/aee97b16-db03-4b60-85f9-c85af11a6ca7)
44. Now let's add Users to your user group.
45. Choose Users from the left-hand navigation panel.
46. Choose Create user.
47. Let's set up this user! Under User name, enter nextwork-dev-yourname.
48. Tick the checkbox for Provide user access to the AWS Management Console.
49. Uncheck the box for Users must create a new password at next sign-in - Recommended.
![Screenshot 2024-08-13 210032](https://github.com/user-attachments/assets/687513c1-3339-4237-9ecb-9c29ca5c64e2)
![Screenshot 2024-08-13 210516](https://github.com/user-attachments/assets/3a00d174-0db8-49e3-b58d-ab14825f5e31)
50. Select Next when you're ready!
51. To set permissions for your user, we'll simply add it to the user group you've created. Select the checkbox next to nextwork-dev-group.
52. Select Next.
53. Select Create user!
![Screenshot 2024-08-13 210643](https://github.com/user-attachments/assets/763cc63c-404b-4ec5-ba6a-747ac0c2a7ef)

54. it's a success - now you're seeing some specific sign-in details for your new user. Stay on this page.
![Screenshot 2024-08-13 210734](https://github.com/user-attachments/assets/1956527b-926b-470e-bb0f-9bd61452e29f)

# STEP #5

# Test your user's access

55. Copy the Console sign-in URL. Do not close this tab!
56. Open a new incognito window on your browser.
57. Open the new console sign-in URL in your incognito window.
58. Using the User name and Console password given in your IAM tab, let's log in!
![Screenshot 2024-08-13 211754](https://github.com/user-attachments/assets/a3046295-f28c-468c-9c1a-c50cbbfefb49)

59. Welcome back to your AWS console, but this time as the dev user that you've created for yourself.
60. As a new user, you'll notice that some of your dashboard panels are showing Access denied already!
![Screenshot 2024-08-13 211850](https://github.com/user-attachments/assets/aee833bd-fe3b-4d60-bbca-e938882d8fde)

60. Head to your EC2 console, and make sure you're in the same Region as the one where you deployed your two production and development instances.
61. Head to Instances.
62. Select your production instance, and in the Actions dropdown, select Manage instance state.
![Screenshot 2024-08-13 212052](https://github.com/user-attachments/assets/ed699829-8921-4d71-89b7-94ac29b64201)

63. Let's try to stop this instance. Select the Stop option, then Change state.
![Screenshot 2024-08-13 212127](https://github.com/user-attachments/assets/2c9815b6-b222-4a25-adc4-7975b029020a)
64. Select Stop.
![Screenshot 2024-08-13 212158](https://github.com/user-attachments/assets/fdb4ea5b-e3d0-42f1-a45e-e78c7fc23c1d)
65. Now let's try to stop the development instance.
66. Head back to the Instances page, and select the checkbox next to nextwork-development-yourname.
67. Under the Actions drop-down, select Manage instance state.
68. Select Stop, then Change state. Select Stop.
![Screenshot 2024-08-13 212406](https://github.com/user-attachments/assets/06578427-cf8b-4992-a95b-4d97653c4219)

69. Success!

# Delete Your All Resources. 
