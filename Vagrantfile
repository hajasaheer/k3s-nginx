Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"

  # Master node
  config.vm.define "k3s-master" do |master|
    master.vm.hostname = "k3s-master"
    master.vm.network "private_network", ip: "192.168.56.101"
    master.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
      vb.cpus = 2
    end
  end

  # Worker node
  config.vm.define "k3s-worker1" do |worker1|
    worker1.vm.hostname = "k3s-worker1"
    worker1.vm.network "private_network", ip: "192.168.56.102"
    worker1.vm.provider "virtualbox" do |vb|
      vb.memory = 1024
      vb.cpus = 2
    end
  end
end
