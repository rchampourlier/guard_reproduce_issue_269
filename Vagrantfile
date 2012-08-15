Vagrant::Config.run do |config|

  # The box and its URL
  config.vm.box = "lucid32-ruby-1.9.3-p194"

  # Using hostonly network. You can change this if it doesn't fit your environment
  # (no reason it shouldn't).
  config.vm.network :hostonly, "10.10.12.2"

  # Forward a port from the guest to the host, which allows for outside
  # computers to access the VM, whereas host only networking does not.
  config.vm.forward_port 3000, 3000 # port-forwarding for development rails server

  # Seems to fix [issue #455](https://github.com/mitchellh/vagrant/issues/455)
  config.vm.customize ["modifyvm", :id, "--rtcuseutc", "on"]
  config.ssh.max_tries = 10

  # Enables NFS shared folders to improve performance 
  #config.vm.share_folder("v-root", "/vagrant", ".", :nfs => true)
end
