Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/mantic64"

  config.vm.define "controln" do |controln|
    controln.vm.hostname = "controln"
    controln.vm.network "private_network", ip: "192.168.33.10"
    controln.vm.network "public_network", bridge: "eth0"
    controln.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get -y install python3-pip
      apt-get install -y ansible
    SHELL
  end

  config.vm.define "managedn1" do |managedn1|
    managedn1.vm.hostname = "managedn1"
    managedn1.vm.network "private_network", ip: "192.168.33.20"
    managedn1.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get -y install python3-pip
    SHELL
  end

  config.vm.define "managedn2" do |managedn2|
    managedn2.vm.hostname = "managedn2"
    managedn2.vm.network "private_network", ip: "192.168.33.30"
    managedn2.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get -y install python3-pip
    SHELL
  end
end
