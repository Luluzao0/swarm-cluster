Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"

  config.vm.define "master" do |master|
    master.vm.network "private_network", ip: "192.168.50.10"
    master.vm.provision "shell", inline: "curl -fsSL https://get.docker.com -o get-docker.sh && sh get-docker.sh"
  end

  (1..3).each do |i|
    config.vm.define "node0#{i}" do |node|
      node.vm.network "private_network", ip: "192.168.50.1#{i}"
      node.vm.provision "shell", inline: "curl -fsSL https://get.docker.com -o get-docker.sh && sh get-docker.sh"
    end
  end
end
