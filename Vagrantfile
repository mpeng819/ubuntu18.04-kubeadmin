# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  config.vm.box = "ubuntu/bionic64"
  config.vm.provision :shell, inline: <<-SHELL
     apt-get update
     apt-get install -y sshpass
     sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
     service ssh restart
  SHELL
  config.vm.provider "virtualbox" do |v|
      v.memory = 1024
  end

  config.vm.define "master" do | master |
    master.vm.hostname = "master"
    master.vm.base_mac = "08002710BC01"
    master.vm.provider "virtualbox" do |v|
      v.memory = 2048
    end
  end

  config.vm.define "node1" do |node1|
    node1.vm.hostname = "node1"
    node1.vm.base_mac = "08002710BCA1"
  end

  config.vm.define "node2" do |node2|
    node2.vm.hostname = "node2"
    node2.vm.base_mac = "08002710BCA2"
  end

  config.vm.define "node3" do |node3|
    node3.vm.hostname = "node3"
    node3.vm.base_mac = "08002710BCA3"
  end

  config.vm.define "node4" do |node4|
    node4.vm.hostname = "node4"
    node4.vm.base_mac = "08002710BCA4"
  end


end
