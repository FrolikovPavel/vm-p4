# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.winnfsd.uid = 1
  config.winnfsd.gid = 1
  config.vm.box = "ubuntu/jammy64"
  config.vm.synced_folder "./shared", "/vagrant_shared", type: "nfs", create:true, nfs_udp: false, mount_options: ['rw,async,fsc,nolock,tcp,hard']
  config.vm.network "private_network", type: "dhcp", ip: "192.168.57.0"
  
  (1..4).each do |i|
    config.vm.define "vm#{i}" do |vm|

      
      vm.vm.provision "shell", inline: <<-SHELL
        wget -O /tmp/mit-license.html https://mit-license.org
      SHELL
    end
  end
end
