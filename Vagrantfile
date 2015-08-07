# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "chad-thompson/ubuntu-trusty64-gui"
  config.vm.network "forwarded_port", guest: 7990, host: 7990
  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = true
    # Customize the amount of memory on the VM:
    vb.memory = "2048"
  end
  # vagrant plugin install vagrant-puppet-install
  config.puppet_install.puppet_version = "3.8.2"
  #config.vm.provision :puppet, :module_path => "puppet/modules" do |puppet|
  #  puppet.manifests_path = "puppet/manifests"
  #  puppet.manifest_file  = "default.pp"
  #end
  config.vm.provision "puppet" do |puppet|
    puppet.module_path = "puppet/modules"
    puppet.manifests_path = "puppet/manifests"
    puppet.manifest_file = "default.pp"
  end  
end
