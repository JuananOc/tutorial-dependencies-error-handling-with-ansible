Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.network "forwarded_port", guest: 9000, host: 9000

  config.vm.provider "virtualbox" do |vb|
    # Customize the amount of memory on the VM:
    vb.memory = "2048"
  end

  config.vm.define "prueba" do |prueba|
    prueba.vm.hostname = "prueba"
    prueba.vm.provision "ansible" do |ansible|
      ansible.verbose = 'vvv'
      ansible.playbook = "ansible/playbook.yml"
      ansible.inventory_path = "ansible/environments/development/inventory"
    end
  end
end
