# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  (1..3).each do |i|
    config.vm.define "vm-#{i}" do |node|
      config.vm.box = "ubuntu/focal64"
      config.vm.hostname = "vm-#{i}"
      config.ssh.keep_alive = true
      config.vm.network "public_network", ip: "192.168.100.#{i}"
      config.vm.provision "file", source: "./authorized_keys", destination: "~/.ssh/authorized_keys"
      config.vm.provider "virtualbox" do |vb|
        vb.name = "vm-#{i}"
        vb.cpus = 4
        vb.memory = "3048"
        vb.gui = false
    end
  end
end
end