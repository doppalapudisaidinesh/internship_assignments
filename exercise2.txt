
Vagrant.configure("2") do |config|
  config.vm.provision "shell", inline: "echo Hello"
  
  config.vm.define "db" do |db|
    db.vm.box = "ubuntu/trusty64"
    db.vm.network "private_network", ip: "192.168.33.20"
    db.vm.synced_folder "C:/Users/saidinesh.d/assignments/assignment1/exercise1/shared", "/shared_data"
    db.vm.network "public_network"
    db.vm.provider "virtualbox" do |vb|
        vb.memory = 1048
        vb.cpus = 2
    end
  end
  
  config.vm.define "apache" do |apache|
    apache.vm.box = "ubuntu/trusty64"
    apache.vm.network "private_network", ip: "192.168.33.30"
    apache.vm.synced_folder "C:/Users/saidinesh.d/assignments/assignment1/exercise1/shared", "/shared_data"
    apache.vm.network "public_network"
    apache.vm.provider "virtualbox" do |vb|
        vb.memory = 2048
        vb.cpus = 1
    end
  end
end