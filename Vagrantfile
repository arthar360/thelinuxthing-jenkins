# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.box_download_insecure = true
  config.vm.box = "base"
      config.vm.define "master" do |master|
       master.vm.box = "ubuntu/xenial64"
	     master.vm.hostname = "master.example.com"
	     master.vm.network "private_network", ip: "172.16.1.100"
       end

      config.vm.define "node1" do |node1|
        node1.vm.box = "ubuntu/xenial64"
	      node1.vm.hostname = "node1.example.com"
	      node1.vm.network "private_network", ip: "172.16.1.201"
        end
        
   	config.vm.provision "shell", inline: <<-SHELL
     	  echo 172.16.1.100 master.example.com master >> /etc/hosts
     	  echo 172.16.1.201 node1.example.com node1 >> /etc/hosts
        echo root:redhat | chpasswd
        sed -i '/PasswordAuthentication/s/no/yes/' /etc/ssh/sshd_config
        sed -i '/PermitRootLogin/s/prohibit-password/yes/' /etc/ssh/sshd_config
        systemctl restart sshd
   	SHELL
end
