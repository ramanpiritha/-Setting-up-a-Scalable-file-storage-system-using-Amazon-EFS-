 # Ex no-4- SETTING UP A SCALABLE FILE STORAGE SYSTEM USING AMAZON ELASTIC FILE SYSTEM
 # Date: 22-11-24
 # Name: Piritharaman R
 # Reg no: 21223230148
 ## AIM
  To  setting up a scalable file storage system using Amazon Elastic File System (EFS) for two EC2 instances in different availability zones. 
## PROBLEM STATEMENT
This experiment demonstrates how to configure Amazon EFS to provide a shared storage solution for two Linux EC2 instances across different availability zones, enabling easy data sharing. The aim is to ensure both instances can mount and access the EFS file system and validate data consistency across instances.
## ALGORITHM
Step 1: Create two EC2 instances in different availability zones. Step 2: Set up a security group that
allows necessary communication between the instances and EFS. Step 3: Create an EFS file system
and mount it to both EC2 instances. Step 4: Ensure that the EC2 instances can access the file system
and share data between them.
## COMMANDS
EC2 Instance 1
```
sudo su
yum install httpd -y
yum install -y amazon-efs-utils
mount -t efs -o tls fs-064645ac116a12816:/ /var/www/html
cd /var/www/html
vi file  # Create a file and add some text
```
EC2 Instance 2
```
sudo su
yum install httpd -y
yum install -y amazon-efs-utils
mount -t efs -o tls fs-064645ac116a12816:/ /var/www/html
cd /var/www/html
ls
cat file  # Verify shared access by reading content created in Instance 1
```
## OUTPUT
Both EC2 instances showing EFS mounting.
![image](https://github.com/user-attachments/assets/3a087613-5c74-4627-9dec-f7297e02894b)
The creation of a file on Instance 1.
![image](https://github.com/user-attachments/assets/c766b858-9892-4da1-9e0a-4faae59f311e)
The display of that file’s contents on Instance 2 to verify shared access
![image](https://github.com/user-attachments/assets/8539521e-7e0b-4ebc-aa77-ab4bd23b25d2)
![image](https://github.com/user-attachments/assets/5d1bc2ce-419c-4d21-8f1a-8cef10478e71)
![image](https://github.com/user-attachments/assets/f2cc6142-0b1a-4132-b047-8479c31e7bf0)

## RESULT
 Successfully set up a scalable file storage system using Amazon EFS shared between two Linux EC2 instances in different availability zones, enabling consistent data sharing.

  


