# -*- mode: ruby -*-
# vi: set ft=ruby :
vmname = "samba-pdc"
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"
  config.vm.hostname = vmname
  config.ssh.keep_alive = true
  config.vm.network "public_network", use_dhcp_assigned_default_route: true
  config.vagrant.plugins = ["vagrant-vbguest"]
  config.vm.provision "file", source: "./authorized_keys", destination: "~/.ssh/authorized_keys"
  config.vm.provider "virtualbox" do |vb|
    vb.name = vmname
    vb.cpus = 2
    vb.memory = "2048"
    vb.gui = false
  end   
end
