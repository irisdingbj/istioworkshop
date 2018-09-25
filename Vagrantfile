Vagrant.configure("2") do |config|
  config.vm.box = "kubeadm-v1.11"
  config.vm.provider :virtualbox do |vb|
    vb.name = "istio-workshop"
    vb.memory = "3584"
    vb.cpus = 2
  end
  config.ssh.password = "vagrant"
  config.ssh.username = "vagrant"
  config.ssh.insert_key = false
  config.vm.network "private_network", ip: "172.28.128.13"
end
