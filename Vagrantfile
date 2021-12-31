# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.



Vagrant.configure("2") do |config|
    
    config.ssh.insert_key = false 
    config.vm.provider :virtualbox do|vb| 
        vb.customize ["modifyvm", :id, "--memory", "2048"] 
    end 


    config.vm.define "raspberrypi1" do |first|
        first.vm.box = "debian/bullseye64"
        first.vm.hostname = "raspberrypi1"
        first.vm.network "forwarded_port", guest: "80", host: "8080"
        first.vm.network :private_network, ip: "192.168.56.200"
        first.verbose = "v"
        first.playbook = "sethost1.yml"
    end


    config.vm.define "raspberrypi2" do |second|
        second.vm.box = "debian/bullseye64"
        second.vm.hostname = "raspberrypi2"
        second.vm.network "forwarded_port", guest: "80", host: "8080"
        second.vm.network :private_network, ip: "192.168.56.201"
        second.verbose = "v"
        second.playbook = "sethost2.yml"
    end


    config.vm.define "raspberrypi3" do |third|
        third.vm.box = "debian/bullseye64"
        third.vm.hostname = "raspberrypi3"
        third.vm.network "forwarded_port", guest: "5432", host: "5432"
        third.vm.network :private_network, ip: "192.168.56.202"
        third.verbose = "v"
        third.playbook = "sethost3.yml"
    end

  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  #  config.vm.network "public_network"
  # config.vm.synced_folder "../data", "/vagrant_data"
end

