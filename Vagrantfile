Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"
  config.vm.network "private_network", ip: "192.168.10.100"
  config.hostsupdater.aliases = ["development.local"]

  # Synced app folder  #host machine folder/virtual machine folder
  config.vm.synced_folder "app", "/app"

  # Provisioning, here we specify where the ansible playbook with all the tasks is located.
  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "environment/node_playbook.yml"
  end
end
