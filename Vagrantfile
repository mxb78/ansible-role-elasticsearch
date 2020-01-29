# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  config.vm.define "elastic" do |elastic|
    #elastic.vm.box = "ubuntu/xenial64"
    elastic.vm.box = "centos/7"
    elastic.vm.hostname = "elastic"

    elastic.vm.network :private_network, ip: "192.168.202.201"

    elastic.vm.provider "virtualbox" do |vb|
      vb.memory = "2024"
    end
  end

  config.vm.synced_folder ".", "/vagrant", type: "rsync",
    rsync__exclude: ".git/"

  config.vm.synced_folder ".", "/vagrant/roles/elastic", type: "rsync",
    rsync__exclude: ".git/"

  config.vm.provision :shell, path: "vagrant_provision.sh"
end
