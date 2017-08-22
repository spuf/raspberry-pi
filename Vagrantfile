Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"

  project_root = "/data"

  config.vm.synced_folder ".", project_root

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "512"
    vb.cpus = "2"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "raspberry-pi.yml"
    ansible.raw_arguments = ["--force-handlers"]
    ansible.sudo = true
    ansible.extra_vars = {
      user: "vagrant"
    }
    # ansible.verbose = "v"
  end
end
