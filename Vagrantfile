# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure(2) do |config|
	config.vm.define "server" do |server|
		server.vm.box = "ubuntu/trusty64"
		server.vm.network :private_network, ip: "192.168.27.100"
		server.vm.provider :virtualbox do |vb|
			 vb.memory = 1024
			 vb.cpus = 2
			 vb.vm.box = "streznik"
			 end
		server.vm.provision :shell, :inline => "apt-get update && apt-get install -y nginx"
		server.vm.provision :shell, :inline => "ln -s /vagrant /usr/share/nginx/html/demo"
		end
	
	config.vm.define "client" do |client|
		client.vm.box = "ubuntu/trusty64"
		client.vm.network :private_network, ip: "192.168.27.101"
		client.vm.provider :virtualbox do |vb|
			 vb.memory = 1024
			 vb.cpus = 1
			 vb.vm.box = "client"
			 end
		end
end