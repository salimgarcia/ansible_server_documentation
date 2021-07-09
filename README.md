# Ansible Server Documentation
Task Description: Read over chapter 1 of Ansible for Devops.
Find the best way to install Ansible as a server and document it. Follow your docs and make sure they work!
This may not need to be the first thing you do. As you read through the first sections the Ansible PDF, you'll likely be able to just work from a command line initially.

- Create an Ubuntu Server VM using the Ubuntu Server template in vmware workstation
- Power on the Ubuntu Server VM and log in
- Run `sudo apt-add-repository -y ppa:ansible/ansible` to add the Ansible repository
- Update the repository by running `sudo apt-get update`
- Install Ansible by running `sudo apt-get install -y ansible`
- Check that Ansible is installed properly by running `ansible --version`
- Create a directory for the inventory file called `test-project`
- Cd into test-project and create a file called `hosts.ini`
- Open the hosts.ini file with a text editor and type the following:
	
```
[example]
*IP Address*
```

- Example is the group of servers being managed and IP Address is the IP of the machine Ansible will configure
- Save `hosts.ini` and exit the text editor
- Go to the Linux machine that will be managed by the Ansible server and enable ssh by running `sudo apt install openssh-server`
- Set the firewall to allow ssh connections by running `sudo ufw allow ssh`
- Go back to the Ansible server and generate an ssh key by `running ssh-keygen -t rsa` and save it in the default location
- Use `ssh-copy-id` to copy the public key to the Linux machine Ansible will manage
- `ssh-copy-id` is part of the OpenSSH package and is a tool that allows you to install an SSH key on a remote server’s authorized keys.
- Run `ansible -i hosts.ini [example] -m ping -u [username]` to test if the Ansible server can run commands on the Linux machine 
