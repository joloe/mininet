# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  #config.ssh.private_key_path = 'D:\mininet\.vagrant.d\insecure_private_key'
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.manage_guest = true
  config.hostmanager.ignore_private_ip = false
  config.hostmanager.include_offline = true
  config.vm.synced_folder ".", "/vagrant", type: "virtualbox"
  
  config.vm.define "switch" do |switch_config|
    switch_config.vm.box = "comnets/mininet"
    switch_config.vm.network "private_network", ip: "192.168.1.102", :netmask => "255.255.255.0"
    switch_config.vm.hostname = "switch"
    switch_config.hostmanager.aliases = "switch"
    switch_config.vm.provider :virtualbox do |v|
      #v.gui = true
      v.customize ["modifyvm", :id, "--name", "switch"]
      v.customize ["modifyvm", :id, "--memory", 1024.to_s]
      v.customize ["modifyvm", :id, "--cpus", 1.to_s]
    end
  end

  #config.vm.define "controller" do |controller_config|
    #controller_config.vm.box = "generic/debian9"
    #controller_config.vm.network "private_network", ip: "192.168.1.103", :netmask => "255.255.255.0"
    #controller_config.vm.hostname = "controller"
    #controller_config.hostmanager.aliases = "controller"
    #controller_config.vm.provider :virtualbox do |v|
      #v.customize ["modifyvm", :id, "--name", "controller"]
      #v.customize ["modifyvm", :id, "--memory", 2048.to_s]
      #v.customize ["modifyvm", :id, "--cpus", 1.to_s]
    #end
  #end

  config.vm.define "client" do |client_config|
    client_config.vm.box = "generic/debian10"
    client_config.vm.network "private_network", ip: "192.168.1.107", :netmask => "255.255.255.0"
    client_config.vm.hostname = "client"
    client_config.hostmanager.aliases = "client"
    client_config.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--name", "client"]
      v.customize ["modifyvm", :id, "--memory", 1024.to_s]
      v.customize ["modifyvm", :id, "--cpus", 1.to_s]
    end
  end

  config.vm.define "server" do |server_config|
    server_config.vm.box = "generic/debian10"
    server_config.vm.network "private_network", ip: "192.168.1.108", :netmask => "255.255.255.0"
    server_config.vm.hostname = "server"
    server_config.hostmanager.aliases = "server"
    server_config.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--name", "server"]
      v.customize ["modifyvm", :id, "--memory", 1024.to_s]
      v.customize ["modifyvm", :id, "--cpus", 1.to_s]
    end
  end

  vagrant_synced_folder_default_type = ""

end
