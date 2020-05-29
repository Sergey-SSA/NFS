# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"
  config.vm.box_check_update = false

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision.yml"
  end

  config.vm.define "server" do |server|
    server.vm.hostname = "server"
    server.vm.network "private_network", ip: "192.168.1.1"
  end

  config.vm.define "client" do |client|
    client.vm.hostname = "client"
    client.vm.network "private_network", ip: "192.168.1.2"
  end
end
