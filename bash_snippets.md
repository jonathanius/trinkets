##### List directory contents recursively including details.
> ls -alR
##### List all running processes.
> ps -aux
##### List resource usage updating every 2 seconds.
> vmstat 2
##### List IO usage information updating every 2 seconds.
> iostat 2
##### Print the detail of mounted filesystems.
> df -h
##### Display the system's available memory.
> free -h
##### List the system's block devices and their mountpoints.
> lsblk
##### List the system's block device attributes
> sudo blkid
##### Disable all swap devices
> sudo swapoff -a
##### Disable swap `<swap_device_path>`
> sudo swapoff `<swap_device_path>`
##### Enable all swap devices
> sudo swapon -a
##### Enable swap `<swap_device_path>`
> sudo swapon `<swap_device_path>`
##### View entries with `<search_string>` in system log files from the last 24 hours.
> journalctl –since=yesterday | grep `<search_string>`
##### Tail syslog printing new entries as they are added.
> tail –f /var/log/syslog
##### List the Boolean values for SELinux policies and filter for those related to the `<httpd>` daemon.
> getsebool -a | grep `<httpd>`
##### List TCP connections to remote addresses.
> netstat -t
##### Update the system's timezone by overwriting the symlink /etc/localtime.
> sudo ln -sf /usr/share/zoneinfo/Australia/Brisbane /etc/localtime
##### Change a machine’s hostname.
> hostnamectl set-hostname <host_name>
##### Measure disk speed by writing a file to the temp directory and delete it afterwrds.
> dd if=/dev/zero of=/tmp/2GBfile bs=1M count=2048; rm /tmp/2GBfile
##### Check the status of `<service_name>` service.
> sudo systemctl status `<service_name>`
##### View the status of the chrony daemon
> sudo systemctl status chronyd
##### Start a `<vm_name>` using the VBoxManage utility in Oracle VirtualBox:
> VBoxManage startvm `<vm_name>` --type headless

## Docker
##### Check the status of the docker service.
> sudo systemctl status docker
##### List images
> sudo docker images
##### Remove an image
> sudo docker rmi `<image_id>`
##### Remove all images
> sudo docker rmi $(docker images -q)
##### Pull the latest version of the registry image.
> sudo docker pull docker.io/registry
##### List running containers
> sudo docker ps
##### Stop a running container
> sudo docker stop `<container_id>`
##### Stop all running containers
> sudo docker stop $(sudo docker ps -q)
##### Remove a container
> sudo docker rm `<container_id>`
##### Remove all containers
> sudo docker rm $(sudo docker ps -aq)
