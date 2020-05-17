* The plan is to install moodle using docker so that we can build, ship and run on any environments.
* Docker can be installed directly on windows but it has its pros and cons. Since we are planning to use linux in real environments it would be better to install Linux in windows. So we will use vagrant as a OS wrapper to provision a ubuntu machine in windows. 
* Step 1: Install Virtual Box from here: https://www.virtualbox.org/wiki/Downloads
* Step 2: Install Vagrant from here: https://www.vagrantup.com/downloads.html
* Step 3: Run "vagrant init ubuntu/xenial64" NOTE: The vagrant init command sets up a Vagrant environment by placing a Vagrant file in the appropriate directory on your machine.
* Step 4: Update the Vagrantfile with config.vm.network "private_network", ip: "192.168.33.10" && config.vm.network "forwarded_port", guest: 80, host: 8000, host_ip: "127.0.0.1"
* Step 5: Run "vagrant up" If this has gone to plan, you should be able to log into your new virtual machine using: 
"vagrant ssh"
* Step 6: Install Docker from here: https://docs.docker.com/engine/install/ubuntu/ and make sure it is up and running
* Step 7: Install Docker compose from here: https://docs.docker.com/compose/install/
* Step 8: Download the docker-compose.yaml from the "local-setup" branch && and run "docker-compose up -d". This provisions two container one for moodle web application and another one is for mariadb. 
* Step 9: Run "docker ps" and wait for ~15 minutes to complete moodle installation. Once it is complete you can access the moodle application with localhost:8000 from the host windows machine. 
