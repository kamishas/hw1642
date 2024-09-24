AWS S3 and EC2 Hosting Report
Part 1: S3 Website Deployment

S3 URL: http://hw1bucket642.s3.us-east-2.amazonaws.com/port.html

Steps for S3 Website Setup:

I began by creating a new S3 bucket, selecting the appropriate region, and using the default configuration settings. I assigned a unique name to the bucket for easy identification.
Following that, I uploaded all the necessary HTML files, with the index.html set as the default landing page. Additionally, I added an error.html file to handle errors during navigation.
To enable static website hosting, I navigated to the properties of the S3 bucket and activated static website hosting, selecting "Host a static website." I provided index.html as the main page and error.html as the error handling page, and saved the settings.
Afterward, I adjusted the public access settings, ensuring all public access blocks were disabled to make the site accessible.
Lastly, I modified the bucket policy to allow public access by adding a policy that granted "s3
" permissions, enabling public read access to all objects within the bucket.
Part 2: EC2 Web Hosting

EC2 URL: http://ec2-18-225-195-94.us-east-2.compute.amazonaws.com/

Steps for EC2 Website Setup:

I started by launching a new EC2 instance, naming it accordingly. I chose Ubuntu as the Amazon Machine Image (AMI) and used the t2.micro instance type, which falls under the free tier. A new key pair was created to facilitate secure SSH access. I ensured that both SSH and HTTP traffic were allowed by adjusting the security group settings.
After launching the instance, I connected to it using SSH. Once connected, I installed Apache using the following commands:
sudo apt-get update
sudo apt-get install apache2
I verified the Apache server's status to confirm it was running properly.
With the web server ready, I uploaded the necessary files using the scp command to transfer files from my local machine to the EC2 instance. The files were placed in the /var/www/html directory, making them accessible through the Apache server.
After completing these steps, the website was successfully hosted and made accessible via the public EC2 URL.
