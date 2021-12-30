# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.



Vagrant.configure("2") do |config|
    config.vm.define "raspberrypi1" do |first|
        first.vm.box = "debian/bullseye64"
        config.vm.network "private_network", ip: "192.168.56.200"
        config.vm.provider "libvirt"  do |vb|
            vb.memory = "1024"
        end
    end


    config.vm.define "raspberrypi2" do |second|
        second.vm.box = "debian/bullseye64"
        config.vm.network "private_network", ip: "192.168.56.201"
        config.vm.provider "libvirt"  do |vb|
            vb.memory = "1024"
        end
    end


    config.vm.define "raspberrypi3" do |third|
        third.vm.box = "debian/bullseye64"
        config.vm.network "private_network", ip: "192.168.56.202"
        config.vm.provider "libvirt"  do |vb|
            vb.memory = "1024"
        end
    end

  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  #  config.vm.network "public_network"
  # config.vm.synced_folder "../data", "/vagrant_data"
end

