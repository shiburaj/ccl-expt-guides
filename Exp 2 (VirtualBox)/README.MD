# Experiment 2 : VirtualBox
Aim: To Host a simple static website on a ubuntu server VM image with NAT networking

## Steps to Perform Experiments
1. Download and Install [VirtualBox](https://www.virtualbox.org/)
2. Download VM Disk Image for Ubuntu Server from [OSBoxes.org](https://www.osboxes.org/ubuntu/)
3. Extract the Downloaded Archive you should get a `.vdi` file. 
4. Start the `VirtualBox` app and Click the `New` button to create a New VM.
5. Give it a name like `Ubuntu Server`
6. While selecting the Hard Disk use the option to select an existing hard disk and locate and select the `.vdi` file.
7. Click Finish and your machine will be ready.
8. Start the VM
9. Click `Settings` for the selected virtual machine and go to networking section and `NAT` must be selected.
10. Under the `Port Forwarding` add following ports 
a. Host Port `2222` to Guest Port `22`
b. Host Port `8080` to Guest Port `80`
c. Any other port as required by your application
11. Use `Putty` to connect to the Guest OS. Open the Putty app and put the IP of the Host OS / localhost and port as `2222`
12. Click Open to connect to the VM and if there is a popup `Accept` it.
13. Run the following commands to setup the server
```
sudo apt update
sudo apt install nginx git -y
sudo service nginx status
cd /var/www/html
sudo rm any-file.html
sudo git clone https://github.com/your-github-portfolio-repo .
```
14. Open the Chrome browser in your Host OS and go to `http://localhost:8080`
