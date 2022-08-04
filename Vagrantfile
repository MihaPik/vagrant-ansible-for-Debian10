Vagrant.configure("2") do |config|
  
  config.vm.box = "debian/buster64"
  config.disksize.size = '10GB'
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "public_network"
  config.vm.synced_folder "./data", "/vagrant"
  config.vm.provider "virtualbox" do |vb|
     vb.memory = "2048"
     vb.cpus = 2
   end
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
  end  
    end