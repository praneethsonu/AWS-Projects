# Visualize A Relational Database

# AWS DataBase Part - 1

# Architecture Diagram:

![architecture-diagram](https://github.com/user-attachments/assets/9893af75-beae-471c-aa87-d068d6bcd4a3)

# AWS Services Used:

1. 🛢️ Amazon RDS (Relational Database Service).
2. 🆕 Amazon QuickSight.
3. 👤 Amazon IAM (Identity Access Management).
4. ☁️ Amazon VPC (Virtual Private Cloud).
5. 📏 Security Groups.

Create a relational database and then visualize my data from by database in the AWS Quicksight.

# STEP #1

# Login with your IAM user

Login to AWS

For this project, you'll need your IAM user, not your root user.

1. Login with your IAM Admin User.
2. If you've logged in successfully as your IAM User, skip to the next step.
3. If you don't have an IAM user set up - no worries!
4. Here are the steps to create one:
5. Head to your AWS Account as the root user.
6. Open the AWS IAM console.
7. From the left-hand navigation panel, choose Users.
8. Choose Create user
9. For the User name, use Your name-IAM-Admin‍
10. Make sure to select the checkbox next to Provide user access to the AWS Management Console - optional.‍
11. This does not apply to all accounts, but if you're prompted with a pop up panel that says Are you providing access to a person?, choose I want to create an IAM user.
12. For the console password, choose Custom password 
13. Type in a password that you will be able to remember/access in the future.
14. Deselect the checkbox for Users must create a new password at next sign-in - Recommended

Choose Next 

In the permissions set up page, choose Attach policies directly

From the list of Permissions policies, select AdministratorAccess.

Choose Next

Choose Create user

Voilà - you've just created your new user! Stay on this page.


Choose Download .csv file

Copy the Console sign-in URL

Now you're ready to start using your IAM user. 🏁

Log out of your root user's AWS Account.

Paste and go to your copied console sign-in URL.

Open your downloaded .csv file containing your user's access instructions.

Log in using your IAM user's username and password in the .csv file.

# STEP #2

# Create a Relational Database
