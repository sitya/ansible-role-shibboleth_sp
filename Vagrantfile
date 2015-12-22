# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "test", primary: true, autostart: true do |test|
    test.vm.box = "trusty64"

    test.vm.network "forwarded_port", guest: 80, host: 9080
    test.vm.network "forwarded_port", guest: 443, host: 9081
    test.vm.network "forwarded_port", guest: 8080, host: 9082

    test.vm.provision "ansible" do |ansible|
      ansible.playbook = "test.yml"
#      ansible.verbose = "vvv"
    end
  end

  config.vm.define "f23", primary: false, autostart: false do |f23|
    f23.vm.box = "fedora-23"

    test.vm.network "forwarded_port", guest: 80, host: 8080
    test.vm.network "forwarded_port", guest: 443, host: 8081

    f23.vm.provision "ansible" do |ansible|
      ansible.playbook = "test.yml"
    end
  end

  config.vm.define "centos70", primary: false, autostart: false do |centos70|
    centos70.vm.box = "chef/centos-7.0"

    test.vm.network "forwarded_port", guest: 80, host: 8080
    test.vm.network "forwarded_port", guest: 443, host: 8081

    centos70.vm.provision "ansible" do |ansible|
      ansible.playbook = "test.yml"
      ansible.verbose = "vvv"
    end
  end

end
