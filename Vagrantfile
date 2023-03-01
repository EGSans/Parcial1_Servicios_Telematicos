Vagrant.configure("2") do |config|
   config.vbguest.installer_options = { allow_kernel_upgrade: true } 
   config.vm.define :cliente do |cliente|
     cliente.vm.box = "centos/stream8"
     cliente.vm.network :private_network, ip: "192.168.50.2"
     cliente.vm.hostname = "cliente"
     cliente.vm.synced_folder ".", "/vagrant", type: "rsync"
     cliente.vm.provider "virtualbox" do |v|
        v.cpus = 2 
     end
   end
   config.vm.define :parcial do |parcial|
     parcial.vm.box = "centos/stream8"
     parcial.vm.network :private_network, ip: "192.168.50.3"
     parcial.vm.hostname = "parcial"
     parcial.vm.synced_folder ".", "/vagrant", type: "rsync"
     parcial.vm.provider "virtualbox" do |v|
        v.cpus = 2 
     end
   end
    Vagrant::Config.run do |config|
      config.vm.forward_port 80, 4567
    end
 end