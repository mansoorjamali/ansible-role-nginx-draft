# -*- mode: ruby -*-
# vi: set ft=ruby :

HOSTNAME = "webserver.test"

Vagrant.configure("2") do |config|
  config.vm.box = "base"


  config.vm.hostname = HOSTNAME
  config.vm.network "forwarded_port", guest: 22, host: 50022
  config.vm.network "forwarded_port", guest: 80, host: 50080

  config.vm.provision "ansible"do |ansible|
    ansible.playbook = "site.yml"

  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider "virtualbox" do |vb|
    vb.name = HOSTNAME
    end
  end
end

