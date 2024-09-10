Vagrant.configure("2") do |config|

config.vm.define "dockerhost-tperk" do |dockerhost|
  dockerhost.vm.box = "generic/debian12"
  dockerhost.vm.network "public_network"
  dockerhost.vm.network "private_network", ip: "10.10.10.130", virtualbox__intnet: "ansible_lab"
  dockerhost.vm.hostname = "dockerhost-tperk"
  dockerhost.vm.synced_folder "./ansible_data", "/vagrant_data"
  dockerhost.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "8192"]
    vb.customize ["modifyvm", :id, "--cpus", "4"]
		vb.name = "DOCKERHOST-TPERK"
    end
  dockerhost.vm.provision "shell", inline: <<-SHELL
    apt-get update 
    apt-get install -y git fish curl tmux mc wget tree
	curl -fsSK https://get.docker.com -o get-docker.sh
	sh ./get-docker.sh
  SHELL
  end
  
config.vm.define "ansible-tperk" do |ansible|
  ansible.vm.box = "generic/debian12"
  ansible.vm.network "public_network"
  ansible.vm.network "private_network", ip: "10.10.1+.131", virtualbox__intnet: "ansible_lab"
  ansible.vm.hostname = "ansible-tperk"
  ansible.vm.synced_folder "./ansible_data", "/vagrant_data"
  ansible.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]
		vb.name = "ANSIBLE-TPERK"
    end
  ansible.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y git ansible fish tmux mc wget tree sshpass yamllint ansible-lint
  SHELL
  end

config.vm.define "ubuntu-tperk" do |ubuntu|
  ubuntu.vm.box = "generic/ubuntu1804"
  ubuntu.vm.network "public_network"
  ubuntu.vm.network "private_network", ip: "10.10.10.132", virtualbox__intnet: "ansible_lab"
  ubuntu.vm.hostname = "ubuntu-tperk"
  ubuntu.vm.synced_folder "./ansible_data", "/vagrant_data"
  ubuntu.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpus", "1"]
		vb.name = "UBUNTU-TPERK"
    end
  ubuntu.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y git fish tmux mc wget tree
  SHELL
  end
  
config.vm.define "centos-tperk" do |centos|
  centos.vm.box = "generic/centos9s"
  centos.vm.network "public_network"
  centos.vm.network "private_network", ip: "10.10.10.133", virtualbox__intnet: "ansible_lab"
  centos.vm.hostname = "centos-tperk"
  centos.vm.synced_folder "./ansible_data", "/vagrant_data"
  centos.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpus", "1"]
		vb.name = "CENTOS-TPERK"
    end
  centos.vm.provision "shell", inline: <<-SHELL
    dnf update
    dnf install -y git fish tmux mc wget tree
  SHELL
  end
  
config.vm.define "opensuse-tperk" do |opensuse|
  opensuse.vm.box = "generic/opensuse42"
  opensuse.vm.network "public_network"
  opensuse.vm.network "private_network", ip: "10.10.10.134", virtualbox__intnet: "ansible_lab"
  opensuse.vm.hostname = "opensuse-tperk"
  opensuse.vm.synced_folder "./ansible_data", "/vagrant_data"
  opensuse.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpus", "1"]
		vb.name = "OPENSUSE-TPERK"
    end
  opensuse.vm.provision "shell", inline: <<-SHELL
    zypper update
    zypper install -y git fish tmux mc wget tree
  SHELL
  end
end