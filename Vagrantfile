Vagrant.configure("2") do |config|

  # Define a method to configure each machine
  def configure_machine(config, name, cpus, gui)
    config.vm.define name do |machine|
      machine.vm.box = "bento/ubuntu-20.04-arm64"
      #machine.vbguest.installer_options = { allow_kernel_upgrade: true }
      machine.vm.network "private_network"
      machine.vm.hostname = name
      machine.vm.provider "vmware_desktop" do |vb|
        vb.memory = "1024" 
        vb.cpus = cpus
        vb.gui = gui
      end
    end
  end

  # Configure ansible-control machine
  configure_machine(config, "ansible-control", 2, true)

  # Configure db01 machine
  configure_machine(config, "db01", 1, true)

  # Configure web01 machine
  configure_machine(config, "web01", 1, true)

  # Configure web02 machine
  configure_machine(config, "web02", 1, true)

  # Configure loadbalancer machine
  configure_machine(config, "loadbalancer", 1, true)

end
