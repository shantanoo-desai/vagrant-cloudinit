# -*- mode: ruby -*-
# vi: set ft=ruby :
unless Vagrant.has_plugin?("vagrant-env")
  raise 'install vagrant-env plugin using vagrant plugin install...'
end

VAGRANT_COMMAND = ARGV[0]

Vagrant.configure("2") do |config|
  # install plugin for env vars: vagrant plugin install vagrant-disksize
  config.env.enable # needed for Cloud-Init experimental setup
  
  # Base Ubuntu 20.04 LTS Image	
  config.vm.box = "ubuntu/focal64"

  # Do not check for Updates
  config.vm.box_check_update = false
  
  # cloud-init script
  config.vm.cloud_init do |cloud_init|
    cloud_init.content_type = "text/cloud-config"
    cloud_init.path         = "cloud-init-test"
  end

  if VAGRANT_COMMAND == "ssh"
    config.ssh.username = 'user'
  end
end
