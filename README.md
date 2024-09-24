AWS S3 and EC2 Hosting Report
Part 1: S3 Website Deployment

S3 URL: http://hw1bucket642.s3.us-east-2.amazonaws.com/port.html

To get my website up and running on AWS S3, I followed these steps:

Create an S3 Bucket: First, I logged into the AWS Management Console and created an S3 bucket. I picked the region closest to me, used the default settings, and gave the bucket a unique name.

Upload Files: I uploaded the necessary files for the website, with index.html being the main page visitors would see first. I also added an error.html file to handle any errors that may come up while browsing.

Enable Static Website Hosting: After uploading, I enabled static website hosting in the S3 settings. I went into the properties of the bucket, clicked on "Static Website Hosting," and selected the option to host a static website. I made sure to set index.html as the homepage and error.html as the error page.

Make the Website Public: S3 doesn't make your site public by default, so I had to change the settings to allow public access. I went to the permissions section, disabled all the blocks that prevented public access, and updated the settings.

Set the Bucket Policy: Lastly, I had to add a bucket policy to allow public users to view the site. I copied and pasted a policy that gives anyone permission to read the files from the bucket, making the website accessible to everyone.

That’s it! Once everything was configured, my website was live and ready to be viewed through the S3 link.

Part 2: EC2 Web Hosting

EC2 URL: http://ec2-18-225-195-94.us-east-2.compute.amazonaws.com/

To host my website on an EC2 instance, here’s what I did step-by-step:

Launch an EC2 Instance: I started by creating an EC2 instance through the AWS console. I chose Ubuntu as the operating system (Amazon Machine Image or AMI) and went with the free t2.micro instance type. I also created a new key pair to securely connect to the server later on. Then, I made sure that both SSH and HTTP traffic were allowed by adjusting the security group settings.

Connect to the Instance: After the instance was up and running, I connected to it via SSH using the key pair I created earlier. I opened up my terminal, used the SSH command, and successfully logged into the EC2 server.

Install Apache Web Server: With access to the server, the next step was to install Apache. I ran a couple of simple commands:

First, I updated the package list with sudo apt-get update.
Then, I installed Apache with sudo apt-get install apache2.
I double-checked that Apache was running by using service apache2 status.
Upload My Website Files: Once Apache was set up, I transferred my website files from my local computer to the EC2 instance using the scp command. This allowed me to copy the files to the server's /var/www/html directory, which is where Apache looks for files to serve to the public.

Once the files were in place, the website was available for anyone to visit through the public EC2 link.

That’s how I got my website hosted using both S3 and EC2 on AWS! If you follow these steps, you should be able to do it too.
