################
# -*- mode: ruby -*-
# vi: set ft=ruby :

require 'rbconfig'
ROLE_NAME = 'dhcp'

Vagrant.configure("2") do |config|
 config.vm.define :dhcpsrv do |dhcpsrv|
    dhcpsrv.vm.box = "bento/ubuntu-18.04"
    dhcpsrv.vm.hostname = "dhcpsrv"
    dhcpsrv.vm.network "public_network", bridge: "vmbr76", ip: "192.168.76.200", netmask: "24"
    
      dhcpsrv.vm.provision 'ansible' do |ansible|
       ansible.compatibility_mode = '2.0'
       ansible.playbook = 'test.yml'
      end
 end

 config.vm.define :clientdhcp1 do |clientdhcp1|
    clientdhcp1.vm.box = "ubuntu/focal64"
    clientdhcp1.vm.hostname = "clientdhcp"
    clientdhcp1.vm.network "public_network", bridge: "vmbr76"
 end

 config.vm.define :clientdhcp2 do |clientdhcp2|
    clientdhcp2.vm.box = "ubuntu/focal64"
    clientdhcp2.vm.hostname = "clientdhcp"
    clientdhcp2.vm.network "public_network", bridge: "vmbr76"
 end


 config.vm.define :clientdhcp do |clientdhcp|
    clientdhcp.vm.box = "ubuntu/focal64"
    clientdhcp.vm.hostname = "clientdhcp"
    clientdhcp.vm.network "public_network", bridge: "vmbr76"
 end



end