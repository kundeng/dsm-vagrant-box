# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  # DSM Vagrant Box

  # Box
  config.vm.box = "kundeng/dsm"


  # Public Network
  #config.vm.network "public_network", auto_config: false
  
  # disable public network??
  #config.vm.network "public_network", bridge: "eno1"
  
  config.vm.network "forwarded_port", guest:5000, host:5000
  config.vm.network "forwarded_port", guest:5005, host:5005
  config.vm.network "forwarded_port", guest:7070, host:7070

  config.vm.network "forwarded_port", guest:22, host:2222, host_ip:"0.0.0.0", id:"ssh", auto_correct:true

  #config.vm.network "private_network", :mac => "0011322CA785"
  
  # Shared Folder
  config.vm.synced_folder '.', '/vagrant', disabled: true

  # SSH
  config.ssh.username = "root"
  config.ssh.password = "vagrant"
  config.ssh.insert_key = true
  config.ssh.shell = "ash"


  config.vm.provider "virtualbox" do |vb|
    # Customize the amount of memory on the VM
    vb.memory = "4096"

    # Attach the boot ISO
    #vb.customize ["storageattach", :id, "--storagectl", "IDE", "--port", "0", "--device", "0", "--type", "hdd", "--medium", "synoboot.vmdk"]
  end

end
