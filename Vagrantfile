# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "node01" do |node01|
    node01.vm.box = "ubuntu/xenial64"
    node01.vm.box_check_update = false
    node01.vm.network "forwarded_port", guest: 8545, host: 8545

    node01.vm.network "private_network", ip: "192.168.33.10"

    node01.vm.provider "virtualbox" do |vb|
      # Display the VirtualBox GUI when booting the machine
      # vb.gui = true
      # Customize the amount of memory on the VM:
      vb.memory = "1024"
      vb.cpus = 1
    end

    node01.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y python-simplejson
    SHELL

    node01.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "dapp.yml"
      # ansible.start_at_task = "npm install ethereumjs-testrpc web3"
    end
  end
end
