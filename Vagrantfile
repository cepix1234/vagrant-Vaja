# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure(2) do |config|
	config.vm.define "server" do |server|
		server.vm.box = "ubuntu/trusty64"
		server.vm.network :private_network, ip: "192.168.27.100"
		server.vm.network :forwarded_port, guest: 80, host: 4567
		server.vm.provider :virtualbox do |vb|
			 vb.memory = 1024
			 vb.cpus = 2
			 end
		server.vm.provision :shell, :inline => "apt-get update && apt-get install -y nginx"
		server.vm.provision :shell, :inline => "ln -s /vagrant /usr/share/nginx/html/demo"
		end
		
	config.vm.define "client" do |client|
		client.vm.box = "debian/jessie64"
		client.vm.network :private_network, ip: "192.168.27.101"
		client.vm.provider :virtualbox do |vb|
			 vb.memory = 1024
			 vb.cpus = 1
			 end
		end
end