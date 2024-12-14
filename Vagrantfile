Vagrant.configure("2") do |config|
  config.vm.box = "focal64.box"

  # Constants.
  SERVERS = 2  # Number of virtual machines
  BRIDGE = "Realtek PCIe GbE Family Controller"  # Network interface for bridged networking

  # Function to configure each host.
  def create_host(config, hostname, ip)
    config.vm.define hostname do |host|
      host.vm.hostname = hostname
      host.vm.network "private_network", ip: ip
      host.vm.network "public_network", bridge: BRIDGE
      host.vm.provision "shell", inline: "apt-get update && apt-get install -y python3"
      yield host if block_given?
    end
  end

  # Create each machine with incremented IP and hostname.
  SERVERS.times do |i|
    create_host(config, "srv#{i + 1}", "192.168.56.#{200 + i + 1}")
  end
end
