# -*- mode: ruby -*-
# vim: set ft=ruby :

MACHINES = {
    :ipa => {
        :box_name => "almalinux/9",
        :ip_addr => '192.168.50.10',
        :cpus => 2,
        :memory => 2048,
    },
    :client1 => {
        :box_name => "almalinux/9",
        :ip_addr => '192.168.50.11',
        :cpus => 1,
        :memory => 512,
    },
    :client2 => {
        :box_name => "almalinux/9",
        :ip_addr => '192.168.50.12',
        :cpus => 1,
        :memory => 512,
    },
}

Vagrant.configure("2") do |config|
  MACHINES.each do |boxname, boxconfig|
      config.vm.define boxname do |box|
          box.vm.box = boxconfig[:box_name]
          box.vm.host_name = boxname.to_s + ".otus.lan"
          box.vm.network "private_network", ip: boxconfig[:ip_addr]
          box.vm.provider :virtualbox do |vb|
            vb.memory = boxconfig[:memory]
            vb.cpus = boxconfig[:cpus] 	        
          end
      end
  end
end
