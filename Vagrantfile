# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-20.04"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: false

  config.vm.provider :virtualbox do |v|
    v.memory = 6000
    v.linked_clone = true
    v.cpus = 2
  end

  config.vm.define "master" do |master|
    master.vm.hostname = "master"
    master.vm.network :private_network, ip: "10.10.10.10"
  end

  config.vm.define "worker1" do |worker1|
    worker1.vm.hostname = "worker1"
    worker1.vm.network :private_network, ip: "10.10.10.11"
  end

  config.vm.define "worker2" do |worker2|
    worker2.vm.hostname = "worker2"
    worker2.vm.network :private_network, ip: "10.10.10.12"
  end
end