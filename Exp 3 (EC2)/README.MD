# Experiment 3 : EC2

***Software*** : AWS Academy Account

***Objective*** : To deploy an ExpressJS app on an EC2 instance. 

***Requirements*** : Each student must develop their own portfolio website with minimum two pages. Landing page must have the name of the student along with their photo and other details that will look good in a portfolio website. Another page must have a list of all the skills known to the student.

***Sample App*** : Sample app for reference DONOT use it every student must make their own portfolio website.

[https://github.com/shiburaj/my-portfolio-express](https://github.com/shiburaj/my-portfolio-express)

## ***Steps to Deploy*** :
1. Go to Services >> Compute >> EC2
2. Create a Key Pair
   - Go to `Network & Security` >> `Key Pairs`
   - Click `Create Key Pair` button
   - Give an appropriate key name
   - Key pair type RSA
   - Format `.ppk`
   - Add tags if required
   - Click `Create key Pair` button
   - Download the key pair file and save it in a safe location
   
![KeyPair](img/keypair.png)

3. Create a Security Group
   - Go to `Network & Security` >> `Security Groups`
   - Click `Create Security Group` button
   - Give an appropriate security group name
   - Give a appropriate description
   - Select the VPC on which the security group will be applied
   - Add the necessary Inbound rules as per the need of the app. (SSH is required to connect to linux machine, Other ports as per requirement of the app)
   - Add tags if required
   - Click `Create Security Group` button

![KeyPair](img/sg1.png)
![KeyPair](img/sg2.png)

4. Create Instance
   - Got to `Instances` >> `Instances`
   - Click `Launch Instances` button
   - Give a name to the Instance
   - Select OS. (Ubuntu)
   - Select Instance Type (t2.micro)
   - Select the created key pair from the dropdown
   - Select the security group that you have created from the dropdown 
   - Configure storage (8gb is fine)
   - Click Launch Instance button 
5. Assign Elastic IP to the Instance
   - Go to Networking & Security >> Elastic IPs
   - Click Allocate Elastic IP Address button
   - Add tags if required
   - Click Allocate button
   - Select the new IP address and go to Actions >> Associate Elastic IP Address
   - Select Resource Type as Instance
   -   Select your instance from dropdown
   -   Select the private ip address from the dropdown
   -   Enable Reassociation
   -   Click Associate button

![KeyPair](img/instance1.png)

6. Connect to the Instance using Putty
   -  Under the Hostname put the Elastic IP of the server
   -  Port will be `22`
   -  Under `Connection` >> `SSH` >> `Auth` >> `Credentials` browse the private key downloaded in Step 2
   -  Click the Open button
   -  When connection for the first time there may be a Firewall exception pop up Accept it.

![KeyPair](img/puty1.png)
![KeyPair](img/puty2.png)

7. Setup the environment for your app on the machine
  ```
  sudo apt update
  sudo apt install nodejs -y
  git clone <your-github-repo-url>
  cd <your-project-directory>
  npm install
  node app.js &
  ```
   - Run apt update to update the package list
   - Install the required platform. Eg: For nodejs app run the following command
   - Clone the code from git repo to the current directory
   - Run npm install to install the dependencies
   - Run node app.js to start the server (Use & at the end to run the server in the background)
8. Open the website in a new tab using the elastic ip and port address 
```
http://<elastic-ip-address>:<port-number>
```

9. (Optional) Shutdown All Services after using
   - Disassociate Elastic IP
   - Release Elastic IP
   - Terminate Instance
   - Delete Security Group
   - Delete Key Pair  