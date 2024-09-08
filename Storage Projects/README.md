# Host A Website On Amazon S3 

# Project Architecture Diagram

![S3 - Architecture](https://github.com/user-attachments/assets/1ade941e-a1f7-4c54-b5c1-0436bcd3ac07)

# Detailed documentation of the project here: 
Link: https://www.linkedin.com/posts/b-praneeth-6b564530a_host-a-website-on-amazon-s3-activity-7227046077667934208-67yb?utm_source=share&utm_medium=member_desktop

# Introducing Today's Project!

What is Amazon S3

Amazon Simple Storage Service (S3) enables the storage of objects that can
be accessible anywhere on the cloud. An object can be any type of file such
as images, videos, documents, and more. The power of S3 lies in its high
availability, scalability,

How I used Amazon S3 in this project

I used S3 for static website hosting. By uploading the HTML file and Folder
where all files like images are present and uploaded in an S3 bucket and
making them publicly accessible on the internet.

# STEP #1

# Create a bucket in Amazon S3

- Go to AWS Management Console, search for S3.

![high-step1 1](https://github.com/user-attachments/assets/183d8a68-ff13-4a61-a03e-57de772a3eab)

- Then choose Create Bucket
- select the "Region closest" to you.
- For Bucket name, enter nextwork-website-project-name. 
- Make sure to replace your name with your name.
- For Object Ownership, choose ACLs enabled.

![image](https://github.com/user-attachments/assets/e9c721de-58bc-4525-8c88-2ae2845ffe5c)

# What are ACLs (Access Control Lists)?

An ACL = is a set of rules that decides who can get access to a resource.

- Choose Bucket owner preferred.
- For Block Public Access settings for this bucket,  clear the check box for Block all public access.
- Check the box that says 
“I acknowledge that the current settings might result in this bucket and the objects within becoming public.”

![image](https://github.com/user-attachments/assets/6c892f36-d22b-42d6-835a-df12cad36034)

- For Bucket Versioning, choose Enable
- Choose Create Bucket.

![image](https://github.com/user-attachments/assets/929174d5-f5ac-4479-9b62-0f67d575f5de)

# STEP #2

# Upload website content to your bucket

Time to get your website's files in your bucket!

- In the Buckets section, choose the name of your new bucket.
- Upload these files into your bucket, like a HTML file and the Assets & images folder.
- Return to the Amazon S3 console with your bucket page open. Choose the Objects tab
- Choose Upload.
- Choose Add files.
- Choose index.html.
- Choose Add folder
- Choose Upload
- S3 will get to work right away!

![image](https://github.com/user-attachments/assets/6c01da81-ce3b-4cd9-b918-a65a884d880c)

- Your files should upload in a few minutes! Choose Close when you see the green Upload succeeded banner.

![image](https://github.com/user-attachments/assets/58277b4e-6521-4c52-96a2-472ed01bdc5f)

# STEP #3

# Configure a static website on Amazon S3

Now let's set up the bucket for static website hosting!

- Make sure you're back in your bucket's page. If you're not sure, choose buckets on the left hand side navigation bar, and then choose the bucket you created for this project.
- Choose the Properties tab.
- Scroll allllllllll the way down to the Static website hosting panel.
- Choose Edit.
- Configure the following settings:
     . Static web hosting: Choose Enable.
     . Hosting type: Choose Host a static website.
     . Index document: Enter index.html.

![image](https://github.com/user-attachments/assets/94db7c78-c014-4e7e-8b35-620a0d35f123)

- Choose Save changes.
- In the Static website hosting panel under bucket website endpoint, copy the URL.
- Use ACLs to make objects in your S3 bucket public
- Let's make the uploaded objects publicly accessible so users can view your website.
- Keep the error message tab open and switch back to the Amazon S3 console tab.
- Would you still remember how to view your S3 bucket's objects? Try finding your bucket's Objects page and making your objects public using ACLs.
- Go to Objects tab.
- Select the checkboxes next to your index.html file and the folder of website assets.
- In the Actions dropdown, choose Make public using ACL.

![image](https://github.com/user-attachments/assets/fdfa6842-d259-43db-a04b-ad00560f8f49)

- Choose Make public.
- Once the green banner pops up, choose close

![image](https://github.com/user-attachments/assets/c243fd18-afd1-432b-a742-ee2304d9ca9e)

- Now go to your browser in the search bar and paste the URL copied, Press enter.

# Website Hosted

![image](https://github.com/user-attachments/assets/d37e2f88-1b81-47c2-abee-6a50959dadc1)

# Delete your resources
- delete bucket and its all files.

