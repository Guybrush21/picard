Vagrant.require_version ">= 1.8.0"

Vagrant.configure(2) do |config|
  
  config.vm.define "riker" do |riker|
    riker.vm.disk :disk, size: "80GB", primary: true
    riker.vm.box = "centos/7"  
    riker.vm.hostname = 'riker'
    riker.vm.network :private_network, ip: "192.168.56.210"
  end

  config.vm.define "worf" do |worf|
    worf.vm.disk :disk, size: "80GB", primary: true
    worf.vm.box = "centos/7"  
    worf.vm.hostname = 'worf'
    worf.vm.network :private_network, ip: "192.168.56.211"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "playbook.yml"    
    ansible.limit = 'all'
  end
end