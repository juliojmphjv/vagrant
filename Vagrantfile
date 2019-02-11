VERSION = "2"

Vagrant.configure(VERSION) do |config|
    config.vm.box = "centos/7"

    config.vm.define :teste1 do |teste1|
        teste1.vm.provider "virtualbox" do |v|
            v.memory = 1024
            v.cpus = 1
        end
        teste1.vm.hostname = "teste1"
        teste1.vm.network :private_network, :ip => "192.168.33.100"
        teste1.vm.synced_folder "ansible", "/ansible"
        teste1.vm.synced_folder ".", "/vagrant", disabled: true

        teste1.vm.provision "ansible_local" do |ansible|
            ansible.provisioning_path = "/ansible"
            ansible.playbook = "playbook.yml"
        end
    end

    
    config.vm.define :teste2 do |teste2|
        teste2.vm.provider "virtualbox" do |v|
            v.memory = 1024
            v.cpus = 1
        end
        teste2.vm.hostname = "teste2"
        teste2.vm.network :private_network, :ip => "192.168.33.101"
        teste2.vm.synced_folder "ansible", "/ansible"
        teste2.vm.synced_folder ".", "/vagrant", disabled: true

        teste2.vm.provision "ansible_local" do |ansible|
            ansible.provisioning_path = "/ansible"
            ansible.playbook = "playbook.yml"
        end
    end
end
