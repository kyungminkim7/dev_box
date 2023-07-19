# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.ssh.forward_agent = true

  # Requires hostmanager plugin
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.manage_guest = true
  config.hostmanager.ignore_private_ip = false
  config.hostmanager.include_offline = true

  config.vm.define "dev" do |dev|
    dev.vm.box = "ubuntu-22.04-x86_64"
    dev.vm.hostname = "dev-ubuntu-2204"

    dev.vm.network "private_network", type: "dhcp"

    dev.vm.provider "virtualbox" do |vb|
      vb.memory = 4096
    end

    dev.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "playbook.yml"
    end
  end
end
