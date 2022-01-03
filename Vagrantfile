# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.



Vagrant.configure("2") do |config|
    
    config.ssh.insert_key = false 

    config.vm.provider "virtualbox" do |vb|
        vb.memory = "2404"
        vb.cpus = "2"
    end

    config.vm.provision "ansible" do |ansible|
        ansible.verbose = "v"
        ansible.playbook = "sethost1.yml"
        # ansible.tags="web,database"
    end

    # config.vm.define "host1" do |first|
    #     first.vm.box = "debian/bullseye64"
    #     first.vm.hostname = "host1"
    #     first.vm.network "forwarded_port", guest: "80", host: "8080"
    #     first.vm.network :private_network, ip: "192.168.56.200"
    # end


    config.vm.define "host3" do |third|
        third.vm.box = "debian/bullseye64"
        third.vm.hostname = "host3"
        third.vm.network "forwarded_port", guest: "5432", host: "5432"
        third.vm.network :private_network, ip: "192.168.56.202"
    end
    
    config.vm.define "host2" do |second|
        second.vm.box = "debian/bullseye64"
        second.vm.hostname = "host2"
        second.vm.network "forwarded_port", guest: "80", host: "8081"
        second.vm.network :private_network, ip: "192.168.56.201"
    end




  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  #  config.vm.network "public_network"
  # config.vm.synced_folder "../data", "/vagrant_data"
end

