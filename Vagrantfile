# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.define "master-vm" do |ma|
    ma.vm.box = "bionic.box"
    ma.vm.hostname = "master"
    ma.vm.network "private_network", ip: "192.168.10.11"

    ma.vm.provider "libvirt" do |qemu|
      qemu.memory = "2048"
      qemu.cpus = 2
    end

    ma.vm.provision "shell", run: "always", inline: <<-SHELL
          echo "Hello, From Master Node"
    SHELL

  end

  config.vm.define "workerone" do |wk1|
    wk1.vm.box = "bionic.box"
    wk1.vm.hostname = "firstworker"
    wk1.vm.network "private_network", ip: "192.168.10.12"

    wk1.vm.provider "libvirt" do |qemu|
      qemu.memory = "1024"
      qemu.cpus = 1
    end

    wk1.vm.provision "shell", run: "always", inline: <<-SHELL
          echo "Hello, From First Worker"
    SHELL

  end

  config.vm.define "workertwo" do |wk2|
    wk2.vm.box = "bionic.box"
    wk2.vm.hostname = "secondworker"
    wk2.vm.network "private_network", ip: "192.168.10.13"

    wk2.vm.provider "libvirt" do |qemu|
      qemu.memory = "1024"
      qemu.cpus = 1
    end

    wk2.vm.provision "shell", run: "always", inline: <<-SHELL
          echo "Hello, From Second Worker"
    SHELL

  end

end
