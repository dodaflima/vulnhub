# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/bullseye64"
  config.vm.network "private_network", ip: "192.168.58.10"
  config.vm.synced_folder "data/", "/src"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.check_guest_additions = false
    vb.name = "vuln_hub"
    vb.cpus = "1"
    vb.memory = "1024"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "playbook.yml"
  end
end
