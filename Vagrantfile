require_relative './key_authorization'

Vagrant.require_version ">= 2.2.0"

Vagrant.configure(2) do |config|
  authorize_key_for_root config, '~/.ssh/id_dsa.pub', '~/.ssh/id_rsa.pub'
  config.vm.box = "centos/7"
  config.vm.disk :disk, size: "80GB", primary: true
  config.vm.provision "shell", inline: "sudo yum install python3 -y"
  
  {
    'riker'    => '192.168.56.210',
    'worf'   => '192.168.56.211',    
  }.each do |short_name, ip|
    config.vm.define short_name do |host|
      host.vm.network 'private_network', ip: ip
      host.vm.hostname = "#{short_name}.uss"
    end
  end
end

