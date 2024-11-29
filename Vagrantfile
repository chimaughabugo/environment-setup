# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Specify the Vagrant box and version
  config.vm.box = "ubuntu/jammy64"
  config.vm.box_version = "20241002.0.0"

  # Forward port 80 from the guest to 8080 on the host
  config.vm.network "forwarded_port", guest: 80, host: 8080

  # Uncomment and configure the private network for host-only access
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Uncomment and configure the public network for bridged networking
  # config.vm.network "public_network"

  # Disable default synced folder (to prevent syncing the Vagrantfile directory)
  config.vm.synced_folder ".", "/vagrant", disabled: true

  # Additional shared folder example (customize as needed)
  # config.vm.synced_folder "../shared_data", "/shared_data"

  # Configure the VirtualBox provider
  config.vm.provider "virtualbox" do |vb|
    # Uncomment to enable the VirtualBox GUI during boot
    # vb.gui = true

    # Configure VM memory and CPUs
    vb.memory = "1024"
    vb.cpus = 2
  end

  # Provision the machine with necessary software
  config.vm.provision "shell", inline: <<-SHELL
    # Update package list and install required software
    apt-get update
    apt-get install -y git awscli
  SHELL

end
