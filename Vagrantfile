# Linux for DevOps Lab Setup
$setup_lab = <<SCRIPT

# Enable root login in ssh configuration

sed -i "s/^PermitRootLogin no/PermitRootLogin yes/g" /etc/ssh/sshd_config
sed -i "s/^PasswordAuthentication no/PasswordAuthentication yes/g" /etc/ssh/sshd_config
systemctl restart sshd
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.define "serverA" do |subconfig|
    subconfig.vm.box = "boxomatic/centos-stream-9"
	subconfig.vm.hostname = "serverA"
	subconfig.vm.network "private_network", ip: "192.168.2.10"
    subconfig.vm.provision "shell", inline:$setup_lab
	
	subconfig.vm.provider "virtualbox" do |vb|
		vb.memory = "2048"
	end    
  end

 config.vm.define "serverB" do |subconfig|
    subconfig.vm.box = "boxomatic/centos-stream-9"
	subconfig.vm.hostname = "serverB"
	subconfig.vm.network "private_network", ip: "192.168.2.20"
	subconfig.vm.provision "shell", inline:$setup_lab
  
	subconfig.vm.provider "virtualbox" do |vb|
		vb.memory = "1024"
	end
  end
end
