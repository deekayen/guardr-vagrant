Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 443, host: 1443

  config.vm.provider "virtualbox" do |vb|
    vb.name = "guardr"

    # Display the VirtualBox GUI when booting the machine
    vb.gui = false

    # Customize the amount of memory on the VM:
    vb.memory = "850"
  end

  config.vm.provision "ansible" do |ansible|
#    ansible.verbose = "v"
    ansible.playbook = "playbook.yml"
  end
end
