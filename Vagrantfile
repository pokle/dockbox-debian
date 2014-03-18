# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ffuenf/debian-7.4.0-amd64"

  config.vm.provision "shell", inline: %Q{
    apt-get install netselect-apt -y && 
    netselect-apt --nonfree && 
    mv sources.list /etc/apt/

    # Install docker
    curl http://get.docker.io/ | sh

    # convenience
    usermod -aG docker vagrant
  }

end
