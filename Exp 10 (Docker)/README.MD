# Experiment 10 : Docker

***Software*** : Docker Desktop

***Objective*** : To deploy an ExpressJS app on Docker. 

***Requirements*** : Each student must deploy Express Notes app on Docker. 

***Sample App*** : Sample app for reference DONOT use it directly. Every student must have already forked this repo in RDS experiment. Use the same repo and change RDS to Docker and commit it to the repo. Then use it to deploy the app in Docker.

[https://github.com/shiburaj/my-notes-express](https://github.com/shiburaj/my-notes-express)

## ***Steps to Deploy*** :
1. Download Docker Desktop from [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)
2. Install Docker Desktop
    
    _**Note**: After install the PC will restart. After restart if the engine doesn't start then try restarting the engine. If it doesn't start try reinstalling Docker Desktop again. If during Installation it gives a error like Hardware Virtualization is disabled in BIOS, then restart your PC and go into BIOS and enable Hardware Virtualization then try installing again._

2. Once Docker Desktop engine is running the create a folder anywhere on the desktop and clone the repo of your Notes app.
3. Open the folder in VSCODE
4. Create `.dockerignore` file and add node_modules and package-lock.json to it.
5. Create a Dockerfile
   1. Start by `node:alpine` as base image
   2. Change working directory to `/app`
   3. Copy `package.json` to working directory
   4. Run `npm install`
   5.  Copy everything to the working directory
   6.  Expose the ports used by the app
   7.  Run `node app.js` using CMD or ENTRYPOINT
6. Create a `docker-compose.yml` file. Create services
      1. **app**: Use build to build the Dockerfile, add required environment varaibles, Set the port forwarding, run on a specific network and restart always with depends on `db`.
      2. **db** : Use `mysql` as image. Setup required environment variables and use the same network as app. Create a volume and use it to persist the data.
      3. **pma** : (Optional) Use `phymyadmin`  as image and setup required environment variables and use the same network as `app`.

7. In the terminal run the following command to start the server.
```
docker compose up -d --build
```

1. In the terminal run the following command to stop the server.
```
docker compose down
```
