##  automate the creation of virtual machines using Vagrant.
###  Vagrant is a tool for building and managing virtualized development environments. It allows you to define    the configuration of virtual machine in a simple text file called a Vagrantfile.

#### To create a virtual machine using Vagrant, you typically follow these steps:
- Install Vagrant: from website
- Choose a Base Box : choose a box from vagrant cloud
- Create a Vagrantfile:This is a configuration file written in Ruby that defines how your virtual machine should be configured. It specifies things configuration machine(memory, cpu etc), network settings etc
  
  >vagrant init nom_of_image

- Start the Virtual Machine: Once Vagrantfile configured,can use the vagrant up command to create and start virtual machine.

##exemple: 
      Vagrant.configure("2") do |config|
         config.vm.define "CLI-01" do |cli_01|
            cli_01.vm.box = "almalinux/8"
            cli_01.vm.hostname = "CLI-01"
            cli_01.vm.network "public_network", bridge:"Qualcomm Atheros QCA61x4A Wireless Network Adapter"
            cli_01.vm.provider "virtualbox" do |v|
                  v.cpus = 1 
                  v.memory = 1024
            end
        end
      end

- Command: vagrant up
  
Once your virtual machine is up and running, can manage it using Vagrant commands like vagrant ssh to SSH into the machine, vagrant suspend to pause it, vagrant halt to shut it down, and vagrant destroy to delete it.