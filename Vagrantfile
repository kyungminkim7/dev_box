# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "dev" do |dev|
    dev.vm.box = "ubuntu-22.04-x86_64"
    dev.vm.hostname = "dev-ubuntu-2204"

    dev.ssh.forward_agent = true

    dev.vm.provider "virtualbox" do |vb|
      vb.memory = 4096
    end

    dev.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "playbook.yml"
    end
  end
end
