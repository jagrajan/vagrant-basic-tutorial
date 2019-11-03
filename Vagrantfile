Vagrant.configure('2') do |config|
  config.vm.box = 'bento/ubuntu-16.04'
  config.vm.network 'forwarded_port', guest: 80, host: 8082

  ### Provision ###
  config.vm.provision 'chef_zero' do |chef|
    chef.arguments = "--chef-license accept"
    chef.cookbooks_path = "cookbooks"
    chef.add_recipe 'hello_web'
    chef.nodes_path = 'nodes'
  end
end
