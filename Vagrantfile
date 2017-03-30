# -*- mode: ruby -*-
# vi: set ft=ruby :

  Vagrant.configure("2") do |config|
  
## Modify the cpus and memory to your liking here. If you need to transcode heavily, you may want to increase cpu.
## We will be using a small ubuntu instance and adding plex to it.
  
  config.vm.box = "ubuntu/xenial64"
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 2
  end
    
## Modify below to the IP you want to bind this to on your network
## For most people, behind a router, this means living on the same network as your host machine (desktop/laptop)
## The public_network is deceiving, and should be looked moreso as a bridge.
## This will make Plex available at http://192.168.1.99:32400/web when vagrant up is finished.

  config.vm.network "public_network", ip: "192.168.1.99"
  
## Modify below the folders you want to mount to /movies and /tv, the format is source, mount point.
## I have left some windows examples below, you will want to change the "Z:/tv" and "Z:/movies" to your own tv and movie folders
## Once you setup plex you will choose /tv for TV and /movies for movies

  config.vm.synced_folder "Z:/tv", "/tv"
  config.vm.synced_folder "Z:/movies", "/movies"
  
## Do not remove below line, this kicks off the install of plex via shell & ansible.
## Do not remove the bootstrap.sh or plex_install.yml files in your folder. 
  config.vm.provision :shell, path: "bootstrap.sh"

  end  
  