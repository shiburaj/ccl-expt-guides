# Experiment 4 : EB

***Software*** : AWS Academy Account

***Objective*** : To deploy an ExpressJS app on an Elastic Beanstalk. 

***Requirements*** : Each student must develop their own portfolio website with minimum two pages. Landing page must have the name of the student along with their photo and other details that will look good in a portfolio website. Another page must have a list of all the skills known to the student.

***Sample App*** : Sample app for reference DONOT use it every student must make their own portfolio website.

[https://github.com/shiburaj/my-portfolio-express](https://github.com/shiburaj/my-portfolio-express)

***Preparations*** : Download the code from github in zip format. Extract it in a folder of your choice. Get into the folder and check it one of the following is present in the package.json file.

```
"main": "app.js",

```
or
```
"scripts": {
    "start": "node app.js"
},

```
It is assumed that `app.js` is the entry file. Change it as per your code. Once these changes are done select all the files and create a zip file. DONOT create the zip of the folder.

## ***Steps to Deploy*** :
1. Go to Services >> Compute >> Elastic Beanstalk
2. Click Create Application button
3. Step 1 : Configure Environment
   - Give an appropriate application name
4. Step 2 : Configure Service Access
5. Step 3 : Networking
6. Step 4 : Traffic and Scaling
7. Step 5 : Monitoring
8. Step 6 : Review and Launch

9. Open the website in a new tab using the elastic ip and port address 
```
http://<elastic-ip-address>:<port-number>
```

1. (Optional) Shutdown All Services after using
   - Disassociate Elastic IP
   - Terminate Instance
   - Delete Security Group
   - Delete Key Pair  