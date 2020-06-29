Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.box_version = "1905.1"

  config.vm.provision "ansible_local" do |ansible|
    ansible.limit = 'all'
    ansible.inventory_path = 'hosts'
    ansible.playbook = 'local.yml'
  end

  config.vm.provision :serverspec do |spec|
    spec.pattern = 'test/*_spec.rb' # pattern for test files
  end
end
