# Working with Vagrantfiles
### Vagrantfiles are useful when you want to create Linux virtual machines
## Different Linux flavor Vagrantfiles

#### Software installation
-Install the below software before working with a vagrantfile. If you already have these softwares installed on your local machine; you can skip this part. More importantly, download the version that's comparable to your system.
--install VirtualBox to manage your virtual machine
https://www.virtualbox.org/wiki/Downloads
--install Vagrant 64-bits to work with vagrantfile
https://developer.hashicorp.com/vagrant/downloads
--To launch or create a VM on your local machine, you can use multiple application programs from Microsoft Powershell, GIT, Visual Studio, etc.

Below are different Linux flavor Vagrantfiles that you can use to create a virtual machine on your local machine.
#### Folder: Centos7_vagrantfile_manual_config
This folder contains a custom Vagrantfile which creates a static webpage. Before running the Vagrantfile you can explore the file and see the changes that I made to it. I uncomment the config. VM.network "private_network" because I want to make a custom private network of my own. You can choose any IP address from Class A, Class B, and Class C private IP addresses, but make sure the private IP address is different from other IP addresses on your network. Also, I uncommented the config. VM.network "public_network", but I did not assign any IP address.
--The private IP address of this CentOS machine is: 192.168.20.10
In the shell section of the Vagrantfile, I added some user data to execute when the machine is getting created to automate some of the tasks.

### Launching Centos7 VM
--Open your favorite command-line interface
Create a directory somewhere in your system
--Command: mkdir sampleVM
Move into the directory
--Command: cd sampleVM
Copy the Vagrantfile into the directory and once the Vagrantfile is in the directory: You can use the ls command to make sure.
-Now, you can create the VM
--Command: vagrant up
This command would create your VM and it might take a little longer to finish because the VM is going to execute the user data in the Vagrantfile shell.

Once the process is complete you can verify if the VM was created by running this command:
--Command: vagrant global-status
You can log in to the VM:
--Command: vagrant ssh VM-ID
Once you are login you can look around and run some Linux commands. If you want to visit the hosted webpage, run the below command and get the IP address of the machine. You can use either private or public.
--Command: ip add show
You can paste the IP address in the browser and see the results.
Now, you have a static webpage hosted on a Linux Centos system.
--If you get an error that the system timeout before completing the setup and you are not able to access the webpage. Open VirtualBox and turn off the VM. Once the VM is off, go to the setting section of your VM and click on Network and make sure adapters 2 and 3 have the bridged adapter option selected. Once you are done, run the "vagrant up" command again in your terminal. Now, you can be able to access the webpage.


#### Folder: Ubuntu_vagrantfile_manual_config
This folder contains a custom Vagrantfile for the Ubuntu machine. Feel free to explore the Vagrantfile and compare the difference between a centos machine and an Ubuntu machine.
--Just a hint, the user data are the difference between the two machines.
To launch this Ubuntu machine, just follow the above instructions for launching the centos machine.
Once you are done, you can use the machine IP address to visit the static webpage that's hosted on the machine.

#### Folder: Wordpress_Ubuntu_vagrantfile_config
This folder contains a custom Vagrantfile for the Ubuntu machine. The machine hosted a WordPress website. Running this vagrantfile would automate the manual tasks of creating a WordPress website.

#### Folder: MultiOS_vagrantfile_config
This folder contains a custom Vagrantfile for multiple different Linux flavor machines. Running this Vagrantfile, you can create two (Centos and Ubuntu) machines at once instead of creating them one by one.
