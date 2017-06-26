# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/jessie64"

  #forward guest's 8080 port on hosts 8090
  config.vm.network "forwarded_port", guest: 8080, host: 8090

  #Ansible
  #https://www.vagrantup.com/docs/provisioning/ansible.html
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "abc.yml"
    ansible.inventory_path = "hosts"

    #https://github.com/jlund/mazer-rackham/issues/7#issuecomment-150895952
    ansible.limit = "all"
  end
end
