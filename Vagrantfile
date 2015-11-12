# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.box = "ubuntu/trusty64"
  end

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update -qq
    sudo apt-get dist-upgrade -qq
  SHELL

  config.vm.provision "ansible" do |ansible|
    ansible.extra_vars = {
    }
    ansible.playbook = "playbook.yml"
    ansible.verbose = "vv"
    ansible.sudo = true
  end
end
