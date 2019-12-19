# How to Launch the Programme

1. Download vagrant and virtual box

2. Create a directory using mkdir

3. cd into your directory created
  - clone the file into this too

4. Use the command 'vagrant init' to create a vagrant file in the directory

5. Open 'atom .' to open the vagrant file and to edit it.
  - there should be a vagrant file in this.
  - once in the vagrant file delete all the commented parts leave the 'vagrant.configure ("2")' line and 'end'


6. You now want to configure the vagrant file:

  - 'config.vm.box =' this will configure what box the machine will be brought up against eg. config.vm.box = "ubuntu/xenial64"

  - 'config.vm.network' this configures the network on the machine eg. config.vm.network "private_network", ip: "192.168.10.100"

  - You will need to alias your ip address, to do this you will need ' config.hostsupdater.aliases' which will look like
  config.hostsupdater.aliases = ["development.local"]. The square brackets allows you to list multiple hosts, if you only want one you can use config.vm.hostname.

5. You then need to save this and then reload vagrant 'reload vagrant' and then 'vagrant up' and use 'vagrant ssh' - to update and give you access to the shell.

6. You then need to provision your project which allows you to define the state of the IT infrastructure. To do this you need to create a new file '<file name>.sh' --> it needs to start with '#!/bin/bash'

7. sudo apt-get update -y ( this command updates )
sudo apt-get upgrade -y (this upgrades)
sudo apt-get install nginx -y (this installs nginx)
sudo systemctl start nginx (this starts nginx )

  - this all needs to go into your provisioning.sh file made

8. Clone the app

```
npm install
npm start
```
