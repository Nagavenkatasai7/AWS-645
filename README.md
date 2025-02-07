Hello, 

I hope you are having a wonderful day.

Part 1:

URL: https://classwebsite645.s3.us-east-1.amazonaws.com/SWE-645/HA-645/index.html
index.html

Part 2:

URL: http://3.87.169.171/HA-645/student_survey_form.html
student_survey_form.html 


AWS S3:

1. First, I created a bucket with the name class-website.

2. After that, I uploaded the website folder into the bucket.

3. Now I made a few changes in the permission section to make my website publicly accessible.

4. I first enabled static website hosting in my properties; there I gave my index.html file name and then saved my changes.

5. Then in permissions, I disabled block public access to make the website accessible to the public.

6. Now again in permission I made changes in the object ownership where I enabled access-controlled list (ACL).

7. Then selected all files in the folder and went to ACTIONS and selected make public using ACL.

8. Now the website is available for public access.




AWS EC2 Instance

1. First I created an instance in EC2. With the name classwebsite1. The application OS is Ubuntu, and the AMI was the Amazon Linux 2023 AMI, which is free tier eligible. Instance type as t2.micro 1 vCPU, 1 GiB memory. Create a new key pair class website 1. Then I allowed HTTP traffic in networking settings to host my website. And launched the website.

2. Now as the next step, I connected to the SSH client through my terminal.

3. First I have checked the permission to my PEM file (chmod 400 /Users/nagavenkatasaichennu/Desktop/SWE-645/classwebsite1.pem).

4. Then I entered the file path to my PEM file and the folder that consists of my code (ssh -i "classwebsite1.pem" ubuntu@ec2-3-87-169-171.compute-1.amazonaws.com). Then I was entered into the Ubuntu OS.

5. Now I installed the required package, like Apache (sudo apt install apache2 -y).

6. To add my file, I felt the best way is to clone the files from my git repository(cd /var/www/html/) (sudo git clone sudo git clone https://github.com/Nagavenkatasai7/AWS-645). So I cloned the website files from the GitHub repository.

7. Now I configured the Apache to change the ownership (sudo chown -R www-data:www-data /var/www/html/). And restart the Apache. (sudo systemctl restart apache2)

8. I made sure all the permissions and configurations are correct (sudo nano /etc/apache2/sites-available/000-default.conf).

9. Then I have disabled the Apache default webpage (sudo rm /var/www/html/index.html). 

10. And now I was able to access my website.




