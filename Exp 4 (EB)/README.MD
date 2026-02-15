# Experiment 4 : EB

***Software*** : AWS Academy Account

***Objective*** : To deploy an ExpressJS app on an Elastic Beanstalk. 

***Requirements*** : Each student must fork the below repository and change the Name and Picture before uploading. If you have your own portfolio website in any backend technology like php, python, express etc. will also do.

[https://github.com/shiburaj/my-portfolio-express](https://github.com/shiburaj/my-portfolio-express)

***Preparations*** : Download/fork the code from github in zip format. Extract it in a folder of your choice. Get into the folder and check if one of the following is present in the package.json file.

```
"main": "app.js",

```
or
```
"scripts": {
    "start": "node app.js"
},

```
It is assumed that `app.js` is the entry file. Change it as per your code. Go to pages folder and edit the `index.html` file and change the name and image to your name and image. The image needs to be uploaded in the `/public/images` folder. Once these changes are done select all the files and create a zip file. DONOT create the zip of the folder instead create the zip of all the contents of the folder.

## Steps to Start AWS Academy Lab
1. Go to AWS Academy Website [Click Here](https://awsacademy.instructure.com/login/canvas)
2. Login with your AWS Academy Credentials or use Forgot Password if you cant remember your password.
3. Go to the Cloud Foundations Course
4. Click Modules and scroll down to Sandbox
5. After opening sandbox click the button to open sandbox in a new window.
6. Click the `Start Lab` button to start the Lab.
7. After sometime when the lab starts the timer of 3hrs will start.
8. Click the `AWS` button to go to your AWS Dashboard.


## ***Steps to Deploy*** :
0. Go to `Security Groups` and create a new security group and open two ports namely port `22` for SHH and `3000` for the express app. change as per your app settings.
1. Go to Services >> Compute >> Elastic Beanstalk
2. Click Create Application button
3. Step 1 : Configure Environment
   - Environment Tier : Web server environment
![sep1](./img/eb1.1.png)
   - Give appropriate application name and tags if required
![sep2](./img/eb1.2.png)
   - Environment Info: Name will be auto-populated, select an appropriate unique domain name, Any description if required
![sep1](./img/eb1.3.png)
   - Platform: Choose as per your app
![sep1](./img/eb1.4.png)
   - Application code: Upload the code zipped in the preperation step
![sep1](./img/eb1.5.png)
   - Presets : Single Instance
![sep1](./img/eb1.6.png)

4. Step 2 : Configure Service Access : Select LabRole, vockey, LabInstanceProfile
![sep1](./img/eb2.png)
5. Step 3 : Networking : Select appropriate VPC and subnets. Since the app doesnt require database you can skip database section.
![sep1](./img/eb3.png)
6. Step 4 : Traffic and Scaling : Select the security group you created in `Step 0`. Auto scaling may be configured if required.
7. Step 5 : Monitoring : No change in monitoring
8. Step 6 : Review and Launch

9.  After step 6 wait for the deployment to be complete. Then Open the website in a new tab using the domain provided by EB and port address 
```
http://<elastic-beanstalk-domain-address>:<port-number>
```
If the website is not opening then check if the security group is configured for the port.