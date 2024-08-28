# DevOps Assignment

# Objective:
Set up a Continuous Integration/Continuous Deployment (CI/CD) pipeline with version control, deployment, and release management using industry-standard tools. 
This assignment is designed to test your ability to integrate and automate the DevOps lifecycle within a limited timeframe.

# Solution:
## Setting up a Continuous Integration/Continuous Deployment (CI/CD) pipeline:
### Tools Used :
- AWS for EC2 Instance to deploy the application.
- Jenkins
- GitHub
- Java
### Steps
 - Create an AWS EC2 instance and connect it to the server. ( I have used my own AWS account )
   ![image](https://github.com/user-attachments/assets/0622f0ff-48ad-498c-956a-abd1016c5598)

- Installations needed in AWS server:
     - Java
     - Jenkins
  - Java is needed to run Jenkins. I have used below commands to install java and jenkins in AWS Server
    
    >
    sudo apt update
    sudo apt install openjdk-11-jre
    java -version
    curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
    /usr/share/keyrings/jenkins-keyring.asc > /dev/null
    echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null

    sudo apt-get update 
    sudo apt-get install jenkins
    sudo systemctl start jenkins.service
    sudo systemctl status jenkins
    >
   Open the 8080 port to setup Jenkins and start working with it

  ### Note: Add TCP 8080 rule in the security groups of the AWS Instance
  
  Now Connect to Jenkins. Type the public address of your instance:8080(it's a default port num of Jenkins) and Give sudo cat /var/lib/jenkins/secrets/initialAdminPassword in the server and paste the pwd. Install all the plugins. Now jenkins is ready.
  
  Ex: 44.211.151.171:8080
   ![image](https://github.com/user-attachments/assets/e5d0757a-f5ea-4321-88a8-36c989b09127)

  Now create a job in freestyle project(A freestyle project in Jenkins is a project that spans multiple operations. It can be a build, a script run, or even a pipeline.)

  Add description, select github project and enter githul repo URL where project is there.
  ## Plugins needed
  Git Hub integration and git client ( which is already available )

  Configure Github repo in jenkins as below

  ![image](https://github.com/user-attachments/assets/dbd690ea-a3ff-4f68-87c7-b2812bea28fe)

  ![image](https://github.com/user-attachments/assets/ed51434e-b0f7-411c-99d0-e45736fa4fb2)

  ![image](https://github.com/user-attachments/assets/25b22351-691e-4701-a6f5-97e82e8e6b8b)


  ## Integrating GitHub and Jenkins for Credentials:

  Go to manage jenkins and under system  add git hub personal access token.

  ![image](https://github.com/user-attachments/assets/fb071e9e-5ed8-4d97-aba9-fdece2b12aad)

  ![image](https://github.com/user-attachments/assets/8239cbed-6f81-42b2-8a96-b00e7c1a049b)

  ## Building and deploying the Application :
  Follow the steps to build the app.

  ![image](https://github.com/user-attachments/assets/035b2623-2f1d-451a-b999-c3d1559b8da6)

  ![image](https://github.com/user-attachments/assets/8aa9eb15-db78-49de-a03e-2ba90da3a6a3)

  and click on save.

  Click on build
  and you can see that our basic application whcih prints "hello world" is succesfully built.

  ![image](https://github.com/user-attachments/assets/76ed20cd-8b2f-44ce-93f5-923c14142814)


  ![image](https://github.com/user-attachments/assets/5e012249-1050-457a-865f-d0c3e68edf89)

 ## Deployment triggering automatically using webhook
  ### Setup webhook
    I have followed below steps to setup webhook . Under repo , go to repo setting and under that add webhook in which we need to enter payload url

  I have made some chnages in the code and automatically my build starts running again.

  





  





  

  


       

