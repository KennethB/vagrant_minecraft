# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrant setup for minecraft servers. For use with virtualbox

MEMSIZE = 2048
CPUS = 2

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "minecraft.local"
  #config.vm.box_url = "http://files.vagrantup.com/precise64.box"
	config.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"
  config.vm.provision :shell, :path => "minecraft_bootstrap"

  config.vm.provider "virtualbox" do |v|
    v.memory = MEMSIZE
    v.cpus = CPUS
  end

	config.vm.network "public_network", ip: "192.168.1.205"

	# start minecraft
	config.vm.provision "shell", inline: "service minecraft start", run: "always"
end
