Vagrant.configure("2") do |config|

  # Define a method to configure each machine
  def configure_machine(config, name, ip, cpus, gui)
    config.vm.define name do |machine|
      machine.vm.box = "generic/ubuntu1804"
      machine.vbguest.installer_options = { allow_kernel_upgrade: true }
      machine.vm.network "private_network", ip: ip
      machine.vm.hostname = name
      machine.vm.provider "virtualbox" do |vb|
        vb.memory = "1024" 
        vb.cpus = cpus
        vb.gui = gui
      end
    end
  end

  # Configure ansible-control machine
  configure_machine(config, "ansible-control", "192.168.30.231", 2, true)

  # Configure db01 machine
  configure_machine(config, "db01", "192.168.30.232", 1, true)

  # Configure web01 machine
  configure_machine(config, "web01", "192.168.30.233", 1, true)

  # Configure web02 machine
  configure_machine(config, "web02", "192.168.30.234", 1, true)

  # Configure loadbalancer machine
  configure_machine(config, "loadbalancer", "192.168.30.235", 1, true)

end
