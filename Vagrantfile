# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

	config.vm.box = "lin19078/ubuntu1810-dev"
  	config.vm.box_version = "1.1.0"

	# Assign this VM to a host-only network IP, allowing you to access it
	# via the IP. Host-only networks can talk to the host machine as well as
	# any other machines on the same network, but cannot be accessed (through this
	# network interface) by any external networks.
	config.vm.network :private_network, ip: "192.168.10.10"
	config.vm.hostname = "vagrant-dev"
	# config.vm.hostname = "vagrant-dev"
	# config.vm.network :public_network

	config.vm.synced_folder "./data", "/data", nfs: true

	config.vm.provider :virtualbox do |virtualbox|
		virtualbox.gui = true
		virtualbox.customize ["modifyvm", :id, "--name", "vagrant-dev"]
		virtualbox.customize ["modifyvm", :id, "--memory", "4096", "--cpus", "4", "--vram", "256"]
		virtualbox.customize ["setextradata", :id, "--VBoxInternal2/SharedFoldersEnableSymlinksCreate/v-root", "1"]
	end
end
