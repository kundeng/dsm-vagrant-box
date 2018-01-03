# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  # DSM Vagrant Box

  # Box
  config.vm.box = "sebask/dsm-vagrant-box"

  # Public Network
  #config.vm.network "public_network", auto_config: false
  config.vm.network "public_network", bridge: "eno1"
  config.vm.network "forwarded_port", guest:5000, host:5000
  config.vm.network "forwarded_port", guest:5005, host:5005
  config.vm.network "forwarded_port", guest:7070, host:7070

  config.vm.network "forwarded_port", guest:22, host:2222, host_ip:"0.0.0.0", id:"ssh", auto_correct:true

  # Shared Folder
  config.vm.synced_folder '.', '/vagrant', disabled: true

  # SSH
  config.ssh.username = "root"
  # config.ssh.password = "vagrant"
  # config.ssh.insert_key = false
  config.ssh.shell = "ash"

  config.vm.provider "virtualbox" do |vb|
    # Customize the amount of memory on the VM
    vb.memory = "2048"

    # Attach the boot ISO
    vb.customize ["storageattach", :id, "--storagectl", "IDE", "--port", "0", "--device", "0", "--type", "dvddrive", "--medium", "XPEnoboot_DS3615xs_5.1-5022.3.iso"]
  end

end
