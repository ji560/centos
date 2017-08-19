Vagrant.configure("2") do |config|
  config.vm.define "centos" do |centos|
    centos.vm.box = "bento/centos-6.9"
    centos.vm.hostname = 'centos'

    centos.vm.network :private_network, ip: "192.168.56.101"
    centos.vm.network :forwarded_port, guest: 22, host: 10122, id: "ssh"

    centos.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 1536]
      v.customize ["modifyvm", :id, "--name", "centos"]
    end
  end

  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.box = "bento/ubuntu-16.04"
    ubuntu.vm.hostname = 'ubuntu'

    ubuntu.vm.network :private_network, ip: "192.168.56.102"
    ubuntu.vm.network :forwarded_port, guest: 22, host: 10222, id: "ssh"

    ubuntu.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 2048]
      v.customize ["modifyvm", :id, "--name", "ubuntu"]
    end
  end

  config.vm.define "kali" do |kali|
    kali.vm.box = "solarium/KaliLinuxRolling"
    kali.vm.hostname = 'kali'

    kali.vm.network :private_network, ip: "192.168.56.103"
    kali.vm.network :forwarded_port, guest: 22, host: 10322, id: "ssh"

    kali.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "kali"]
    end
  end
  config.vm.define "centos", autostart: false
  config.vm.define "ubuntu", autostart: false
  config.vm.define "kali", autostart: false
end
