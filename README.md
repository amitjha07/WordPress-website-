Deploy the 3-tier application in AWS:
1) Deploy DB Service using RDS.
2) Deploy a WordPress website on an Amazon EC2 instance.

-----------------------------------------------------------
Deploy DB Service using RDS:
-----------------------------------------------------------
  Step 1: Go to RDS and click on “Create database”.

  ![image](https://github.com/user-attachments/assets/f63a4f9f-f79a-4e2e-a884-330b3467de43)

  Step 2: Choose a database creation method
    ![image](https://github.com/user-attachments/assets/65c2d4aa-ad10-47d2-997a-088b2380aebd)


  Step 3: Choose the database engine you want to use (e.g., MySQL, 
         PostgreSQL, Oracle, SQL Server, MariaDB, or Amazon Aurora).
    ![image](https://github.com/user-attachments/assets/16f0cd6e-6f33-411f-8cc5-b50f8d8eb3fd)


  Step 4: Select the version and edition of the database engine you want to use

  ![image](https://github.com/user-attachments/assets/294317a5-d158-4c33-b33f-bd5dedfafa5d)


  Step 5: Select the templates you want to use.

  ![image](https://github.com/user-attachments/assets/6968119f-cd8f-4856-8be3-a4d13d63279d)



  Step 6: Configure the database settings such as the database name, username, 
          and password

  ![image](https://github.com/user-attachments/assets/dc5538a0-a84f-4d37-9ab1-580b7b295120)


Step 7: Choose the appropriate instance class based on your performance and 
         storage needs

  ![image](https://github.com/user-attachments/assets/afeabdd0-5e6c-45a9-a417-acd2124d739a)



  Step 8: Select the appropriate VPC and subnet group to launch the database 
          in

  ![image](https://github.com/user-attachments/assets/7907594c-90ac-49a9-b5ed-eaa214a63857)



  Step 9: Configure the database security group to control access to the 
          database
  ![image](https://github.com/user-attachments/assets/674e7ee2-0578-4d1d-9fd5-49d6cea0ed04)




 Step 10: Create the initial database.

  ![image](https://github.com/user-attachments/assets/5622514e-aac0-4e0c-bbe9-b213efe634cb)

  Review and confirm the settings, then launch the database instance


----------------------------------------------------------
Deploy a WordPress website on an Amazon EC2 instance
-----------------------------------------------------------

  Step 1: Launch an EC2 instance using Amazon Linux AMI

  Step 2: Install and start the Apache httpd web server.
     # yum install httpd -y
     # systemctl enable httpd --now

     
  Step 3: Go to the Apache web server web page location and download 
  WordPress and extract it
![image](https://github.com/user-attachments/assets/87b09ec1-d247-4d12-ac7f-aa19225bd57d)
    # tar -xzvf latest.tar.gz
    
  Step 4: Copy all WordPress contents in the Apache httpd web page location.
    ![image](https://github.com/user-attachments/assets/3d1dcf02-706b-492b-825a-ae4784522178)

  Step 5: Make Apache owner for all WordPress content
    ![image](https://github.com/user-attachments/assets/377b7744-139f-4c2a-b505-2b9fcfc7be50)

  ![image](https://github.com/user-attachments/assets/5988d86b-d725-4c7a-b47a-ceabcb79c904)
  Step 6: Download php for running WordPress
    ![image](https://github.com/user-attachments/assets/b6aebb42-49a5-4d41-b0c4-0ced6a982eca)

  Step 6: Edit inbound rules which enable traffic to the RDS instance.

  ![image](https://github.com/user-attachments/assets/ba735947-cc23-4a13-b5f7-53dd3bbc0180)

  Then finally restart the httpd service.
      # systemctl restart httpd

  Now hit the IP of the WordPress instance and they ask about database 
    information
    ![image](https://github.com/user-attachments/assets/2d4ad623-e1ce-49bc-88cd-4d9f05a31b5b)
