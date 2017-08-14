USERNAME = "devel"
HOSTNAME = "devbox"

VAGRANT_COMMAND = ARGV[0]

Vagrant.configure(2) do |config|

  if VAGRANT_COMMAND == "ssh"
    config.ssh.username = USERNAME
  end

  config.vm.box = "boxcutter/ubuntu1604"
  # config.vm.box_url = "<path/to/box/file>"

  config.vm.hostname = HOSTNAME

  config.vm.network "private_network", type: "dhcp"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  # config.vm.network "private_network", ip: "192.168.30.10", type: "static"

  config.vm.synced_folder "./src",  "/home/vagrant/src", create: true
  # config.vm.synced_folder "<host/path>", "<guest/path>", create: true,
  #   owner: "#{USERNAME}", group: "#{USERNAME}", mount_options: ["dmode=755,fmode=644,"]

end
