Vagrant.configure("2") do |config|
  # (Ubuntu 18.04)
  config.vm.define "ubuntu18" do |ubuntu18|
    ubuntu18.vm.box = "ubuntu/bionic64"
    ubuntu18.vm.network "private_network", type: "dhcp"
    ubuntu18.vm.network "forwarded_port", guest: 443, host: 443
    ubuntu18.vm.network "forwarded_port", guest: 80, host: 80
    ubuntu18.vm.network "forwarded_port", guest: 27017, host: 27017
    ubuntu18.vm.provider "virtualbox" do |vb|
      vb.memory = 1024
      vb.cpus = 2
    end
  end

  # (Ubuntu 20.04)
  config.vm.define "ubuntu20" do |ubuntu20|
    ubuntu20.vm.box = "ubuntu/focal64"
    ubuntu20.vm.network "private_network", type: "dhcp"
    ubuntu20.vm.network "forwarded_port", guest: 443, host: 443
    ubuntu20.vm.network "forwarded_port", guest: 80, host: 80
    ubuntu20.vm.network "forwarded_port", guest: 27017, host: 27017
    ubuntu20.vm.provider "virtualbox" do |vb|
      vb.memory = 1024  #
      vb.cpus = 2        
    end
  end

 # (Ubuntu 22.04)
 config.vm.define "ubuntu22" do |ubuntu22|
  ubuntu22.vm.box = "ubuntu/jammy64"
  ubuntu22.vm.network "private_network", type: "dhcp"
  ubuntu22.vm.network "forwarded_port", guest: 443, host: 443
  ubuntu22.vm.network "forwarded_port", guest: 80, host: 80
  ubuntu22.vm.network "forwarded_port", guest: 27017, host: 27017
  ubuntu22.vm.provider "virtualbox" do |vb|
    vb.memory = 1024  #
    vb.cpus = 2        
  end
end

# ( Debian 11 debian/bullseye64)
config.vm.define "debian11" do |debian11|
  debian11.vm.box = "debian/bullseye64"
  debian11.vm.network "private_network", type: "dhcp"
  debian11.vm.network "forwarded_port", guest: 443, host: 443
  debian11.vm.network "forwarded_port", guest: 80, host: 80
  debian11.vm.network "forwarded_port", guest: 27017, host: 27017
  debian11.vm.provider "virtualbox" do |vb|
    vb.memory = 1024  #
    vb.cpus = 2        
  end
end

# ( Debian 12 debian/bookworm64)
# ! not supported need workaround for this
#config.vm.define "debian12" do |debian12|
#  debian12.vm.box = "debian/bookworm64"
#  debian12.vm.network "private_network", type: "dhcp"
#  debian12.vm.network "forwarded_port", guest: 443, host: 443
#  debian12.vm.network "forwarded_port", guest: 80, host: 80
#  debian12.vm.network "forwarded_port", guest: 27017, host: 27017
#  debian12.vm.provider "virtualbox" do |vb|
#    vb.memory = 1024  #
#    vb.cpus = 2        
#  end
#end

end
