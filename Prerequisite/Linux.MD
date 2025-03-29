# Essential Linux Commands for Ubuntu

## System Information
- `uname -a` → Show system information  
- `hostname` → Display the hostname  
- `lsb_release -a` → Get Ubuntu version  
- `uptime` → Check system uptime  
- `whoami` → Show current user  
- `who` → Show who is logged in  

## File and Directory Management
- `pwd` → Print current directory  
- `ls -lah` → List files with details  
- `cd /path/to/directory` → Change directory  
- `mkdir new_folder` → Create a directory  
- `rm filename` → Delete a file  
- `rm -r directory_name` → Remove directory  
- `cp source destination` → Copy files  
- `mv source destination` → Move/rename files  

## File Permissions
- `chmod 755 file` → Change file permissions  
- `chown user:group file` → Change file owner  

## Disk and Storage Management
- `df -h` → Show disk usage  
- `du -sh folder` → Check folder size  
- `mount /dev/sdX /mnt` → Mount a device  
- `umount /mnt` → Unmount a device  

## Process Management
- `ps aux` → List processes  
- `top` / `htop` → Monitor system resources  
- `kill PID` → Kill a process  
- `pkill process_name` → Kill by name  
- `systemctl restart service_name` → Restart a service  

## Networking
- `ip a` → Show network interfaces  
- `ping example.com` → Check connectivity  
- `curl -I example.com` → Get HTTP headers  
- `wget URL` → Download a file  
- `netstat -tulnp` → List open ports  
- `nmap -p 1-65535 localhost` → Scan open ports  

## Package Management
- `sudo apt update` → Update package list  
- `sudo apt upgrade -y` → Upgrade installed packages  
- `sudo apt install package_name` → Install a package  
- `sudo apt remove package_name` → Remove a package  

## User Management
- `adduser username` → Create a new user  
- `deluser username` → Delete a user  
- `passwd username` → Change user password  
- `usermod -aG groupname username` → Add user to a group  
- `groups username` → Check user groups  

## System Monitoring
- `free -h` → Show RAM usage  
- `vmstat` → View CPU statistics  
- `iostat` → Show CPU and disk usage  

## SSH and Remote Access
- `ssh user@remote_ip` → Connect via SSH  
- `scp file user@remote:/path` → Copy files over SSH  
- `rsync -av file user@remote:/path` → Sync files  

## Log Files
- `cat /var/log/syslog` → View system logs  
- `journalctl -xe` → View detailed logs  
- `dmesg | less` → Kernel logs  

## Services & Daemons
- `systemctl start service_name` → Start a service  
- `systemctl stop service_name` → Stop a service  
- `systemctl enable service_name` → Enable auto-start  

## Compression & Archiving
- `tar -cvf archive.tar directory` → Create a tar archive  
- `tar -xvf archive.tar` → Extract tar archive  
- `zip -r archive.zip directory` → Create a zip file  
- `unzip archive.zip` → Extract a zip file  

## Environment & Variables
- `echo $HOME` → Show environment variable  
- `export VAR=value` → Set an environment variable  

## Crontab (Task Scheduling)
- `crontab -e` → Edit scheduled tasks  
- `crontab -l` → List scheduled tasks  

## Firewall Management (UFW)
- `sudo ufw enable` → Enable firewall  
- `sudo ufw allow 22/tcp` → Allow SSH  
- `sudo ufw status` → Check firewall rules