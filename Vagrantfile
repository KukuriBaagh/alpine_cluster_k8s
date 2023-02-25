# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.define "master-vm" do |ma|
    ma.vm.box = "libvirt.box"
    ma.vm.hostname = "master-node"
    ma.vm.network "private_network", ip: "192.168.10.11"

    ma.vm.provider "libvirt" do |qemu|
      qemu.memory = "1024"
      qemu.cpus = 1
    end

    ma.vm.provision "shell", run: "always", inline: <<-SHELL
          echo "Hello, From Master VM"
    SHELL

  end

  config.vm.define "worker1" do |wk1|
    wk1.vm.box = "libvirt.box"
    wk1.vm.hostname = "worker-node1"
    wk1.vm.network "private_network", ip: "192.168.10.12"

    wk1.vm.provider "libvirt" do |qemu|
      qemu.memory = "1024"
      qemu.cpus = 1
    end

    wk1.vm.provision "shell", run: "always", inline: <<-SHELL
          echo "Hello, From Worker One"
    SHELL

  end

  config.vm.define "worker2" do |wk2|
    wk2.vm.box = "libvirt.box"
    wk2.vm.hostname = "worker-node2"
    wk2.vm.network "private_network", ip: "192.168.10.13"

    wk2.vm.provider "libvirt" do |qemu|
      qemu.memory = "1024"
      qemu.cpus = 1
    end

    wk2.vm.provision "shell", run: "always", inline: <<-SHELL
          echo "Hello, From Worker Two"
    SHELL

  end

end
