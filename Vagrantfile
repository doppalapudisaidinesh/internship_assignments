
Vagrant.configure("2") do |config|

 
  config.vm.box = "ubuntu/trusty64"


  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.network "public_network"

  config.vm.synced_folder "C:/Users/saidinesh.d/assignments/assignment1/exercise1/shared", "/shared_data"

  config.vm.provider "virtualbox" do |vb|
     vb.memory = "1024"
  end
   config.vm.provision "shell", inline: <<-SHELL
     apt-get update
     apt-get install -y apache2
   SHELL
end
