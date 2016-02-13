# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.ssh.forward_agent = true

  config.vm.define :node1 do |node|
    node.vm.hostname = "vagrant"
    node.vm.box = "vagrant-centos67"
    node.vm.box_url = "https://github.com/CommanderK5/packer-centos-template/releases/download/0.6.7/vagrant-centos-6.7.box"
    node.vm.network "private_network", ip: "192.168.33.10"
  end

  config.vm.define :node2 do |node|
    node.vm.hostname = "vagrant"
    node.vm.box = "vagrant-centos67"
    node.vm.box_url = "https://github.com/CommanderK5/packer-centos-template/releases/download/0.6.7/vagrant-centos-6.7.box"
    node.vm.network "private_network", ip: "192.168.33.11"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.inventory_path = "hosts"
    ansible.limit = "all"
    ansible.verbose = "vvvv"
  end
end
