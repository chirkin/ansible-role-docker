# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['ANSIBLE_ROLES_PATH'] = "../"

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "bento/ubuntu-16.04"
  config.vm.hostname = "ansible-role-docker"

  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
    v.customize ["modifyvm", :id, "--memory", "256"]
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "tests/vagrant/vagrant.yml"
    ansible.verbose = "vv"
    ansible.limit = "all"
  end
end
