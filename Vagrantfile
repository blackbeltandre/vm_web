Vagrant.configure("2") do |config|
  config.vm.provision "shell", inline: "apt-get update "
  config.ssh.forward_agent = true
   config.ssh.insert_key = false 


  config.vm.define "master" do |master|
    master.vm.box = "generic/ubuntu2004"
    master.vm.box_version = "3.1.16"
    master.vm.network "private_network",ip: "172.168.10.8"
      master.vm.provider "virtualbox" do |v|
        v.memory = 2024
        v.cpus = 4
    end
  end


 config.vm.define "worker" do |worker|
    worker.vm.box = "generic/ubuntu2004"
    worker.vm.network "private_network",ip: "172.168.10.9"
    worker.vm.box_version = "3.1.16"
    worker.vm.provider "virtualbox" do |v|
        v.gui = true
        v.memory = 2024
        v.cpus = 2
     end  
  end
end
# vagrant up --provider virtualbox
