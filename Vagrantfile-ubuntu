# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  (1..3).each do |i|
    config.vm.define "node-#{i}" do |node|
        node.vm.hostname = "node-#{i}"
        node.vm.box = "ubuntu/focal64"
        node.ssh.keep_alive = true
        node.vm.network "private_network", ip: "192.168.56.#{i+10}"
        node.vm.network "public_network", ip: "192.168.100.#{i+10}"
        node.vm.provision "file", source: "./authorized_keys", destination: "~/.ssh/authorized_keys"
        node.vm.provider "virtualbox" do |vb|
          vb.name = "node-#{i}"
          vb.cpus = 4
          vb.memory = "4048"
          vb.gui = false
        end
      end
    end
end