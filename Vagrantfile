VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.hostname = 'nodejs-dev-box'
  config.vm.box = "ubuntu_phusion"
  config.vm.box_url = "https://oss-binaries.phusionpassenger.com/vagrant/boxes/latest/ubuntu-14.04-amd64-vbox.box"

  config.vm.network :forwarded_port, guest: 3000, host: 3005

  config.vm.network :private_network, ip: '192.168.33.10'

  config.vm.synced_folder './', '/vagrant', :mount_options => ['dmode=777', 'fmode=777']

  config.vm.provision "chef_solo" do |chef|
    chef.cookbooks_path = "cookbooks"
    chef.add_recipe "build-essential"
    chef.add_recipe "nodejs"
    chef.add_recipe "java"
    chef.add_recipe "elasticsearch"
    chef.add_recipe "mongodb::10gen_repo"
    chef.add_recipe "mongodb"

    chef.json = {
      "elasticsearch" => {
        "cluster_name" => "elasticsearch_test_chef",
        "bootstrap.mlockall" => false
      }
    }
  end

end
