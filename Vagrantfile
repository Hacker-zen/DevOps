# Number of required machines
SERVERS = 2
# Network interface name for bridge configuration
BRIDGE = "Realtek PCIe GbE Family Controller"

Vagrant.configure("2") do |config|
  config.vm.box = "focal64.box"

  # Function to define a host
  def create_host(config, hostname, ip)
    config.vm.define hostname do |host|
      host.vm.hostname = hostname
      host.vm.network "private_network", ip: ip
      host.vm.network "public_network", bridge: BRIDGE
      host.vm.provision "shell", inline: "apt-get update && apt-get install -y python3"
      yield host if block_given?
    end
  end

  # Create machines based on SERVERS count
  (1..SERVERS).each do |machine_id|
    create_host(config, "srv#{machine_id}", "192.168.56.#{200 + machine_id}")
  end
end
