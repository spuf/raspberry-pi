Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "512"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "raspberry-pi.yml"
    ansible.extra_vars = {
      user: "vagrant"
    }
    # ansible.verbose = "v"
  end
end
