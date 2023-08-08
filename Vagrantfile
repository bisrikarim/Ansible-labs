Vagrant.configure("2") do |config|
  servers=[
      {
        :hostname => "ansible-control",
        :box => "uwbbi/bionic-arm64",
        :ssh_port => '2200',
        :ip => "192.168.11.90",
        :box_version => "1.0.1"
      },
      {
        :hostname => "db01",
        :box => "uwbbi/bionic-arm64",
        :ssh_port => '2201',
        :ip => "192.168.11.91",
        :box_version => "1.0.1"
      },
      {
        :hostname => "web01",
        :box => "uwbbi/bionic-arm64",
        :ssh_port => '2202',
        :ip => "192.168.11.92",
        :box_version => "1.0.1"
      },
      {
        :hostname => "web02",
        :box => "uwbbi/bionic-arm64",
        :ssh_port => '2203',
        :ip => "192.168.11.93",
        :box_version => "1.0.1"
      },
      {
        :hostname => "loadbalancer",
        :box => "uwbbi/bionic-arm64",
        :ssh_port => '2204',
        :ip => "192.168.11.94",
        :box_version => "1.0.1"
      }
    ]

  servers.each do |machine|
      config.vm.define machine[:hostname] do |node|
          node.vm.box = machine[:box]
          node.vm.hostname = machine[:hostname]
          node.vm.box_version = machine[:box_version]
          node.vm.network :private_network
          node.vm.network "forwarded_port", guest: 22, host: machine[:ssh_port], id: "ssh"
          node.vm.provider "vmware_desktop" do |vb|
              vb.gui = true
          end
      end
  end
end