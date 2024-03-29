# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.define "database" do |db|
    db.vm.box = "ubuntu/xenial64"
	db.vm.provider "virtualbox" do |vb|
	  vb.memory = "512"  
	end
    db.vm.hostname = "db01"
    db.vm.network "private_network", ip: "192.168.55.100"
    # MySQL Port nur im Private Network sichtbar
        db.vm.network "forwarded_port", guest:3306, host:3306, auto_correct: false
  	db.vm.provision "shell", path: "db.sh"
  end
  
  config.vm.define "web" do |web|
    web.vm.box = "ubuntu/xenial64"
    web.vm.hostname = "web01"
    web.vm.network "private_network", ip:"192.168.55.101"
	web.vm.network "forwarded_port", guest:80, host:8080, auto_correct: true
	web.vm.provider "virtualbox" do |vb|
	  vb.memory = "512"  
	end     
  	web.vm.synced_folder ".", "/var/www/html"  
	web.vm.provision "shell", inline: <<-SHELL
	  sudo apt-get update
	  sudo apt-get -y install apache2 mysql-client nmap
	  echo '127.0.0.1 localhost web01\n192.168.55.100 db01' > /etc/hosts
	  #  enable tunnelled clear text passwords
	  sudo sed -i -e"s/^PasswordAuthentication no/PasswordAuthentication yes/" /etc/ssh/sshd_config
	  sudo service sshd restart
SHELL
	end 
	# User und Gruppen in alle VM hinzufuegen
	config.vm.provision "shell", inline: <<-SHELL
      sudo groupadd myadmin
      sudo useradd admin01 -g myadmin -m -s /bin/bash 
      sudo useradd admin02 -g myadmin -m -s /bin/bash 
      sudo chpasswd <<<admin01:admin
      sudo chpasswd <<<admin02:admin
	  #  enable tunnelled clear text passwords
	  sudo sed -i -e"s/^PasswordAuthentication no/PasswordAuthentication yes/" /etc/ssh/sshd_config
	  sudo service sshd restart
SHELL

#Firewall 
db.vm.provision "shell", inline: <<-SHELL
	sudo apt-get install ufw -y
	sudo ufw -f enable
	sudo ufw allow from any to any port 3306
	sudo ufw allow from any to any port 22
SHELL

web.vm.provision "shell", inline: <<-SHELL 
	sudo apt-get install ufw -y
	sudo ufw -f enable
	sudo ufw allow from "192.168.55.100" to any port 3306
SHELL
 end
