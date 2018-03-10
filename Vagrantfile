# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"

  # SSH Production
  (1..1).each do |i|
    config.vm.provider "virtualbox" do |vb|
      vb.memory = 1024
      vb.cpus = 2
    end

    config.vm.define "ssh0#{i}.prd" do |server|
      server.vm.hostname = "ssh0#{i}.prd"
      server.vm.network "private_network", ip: "10.0.1.18#{i}"
    end
  end

  # SSH Staging
  (1..1).each do |i|
    config.vm.provider "virtualbox" do |vb|
      vb.memory = 1024
      vb.cpus = 2
    end

    config.vm.define "ssh0#{i}.stg" do |server|
      server.vm.hostname = "ssh0#{i}.stg"
      server.vm.network "private_network", ip: "10.0.1.19#{i}"
    end
  end

  # SSH Development
  (1..1).each do |i|
    config.vm.provider "virtualbox" do |vb|
      vb.memory = 1024
      vb.cpus = 2
    end

    config.vm.define "ssh0#{i}.dev" do |server|
      server.vm.hostname = "ssh0#{i}.dev"
      server.vm.network "private_network", ip: "10.0.1.20#{i}"
    end
  end

  # Provision
  config.vm.provision "shell", path: "provision.sh"
  config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "/home/vagrant/.ssh/authorized_keys"

end
