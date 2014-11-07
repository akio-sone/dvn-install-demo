# version 1 http://vagrantup.com/v1/docs/vagrantfile.html
# version 2 https://docs.vagrantup.com/v2/vagrantfile/index.html

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "puppet-vagrant-boxes-centos-64-x64-vbox4210"
  config.vm.box_url = "http://puppet-vagrant-boxes.puppetlabs.com/centos-64-x64-vbox4210.box"

  config.vm.network  "forward_port", guest:   80, host: 8888
  config.vm.network  "forward_port", guest:  443, host: 9999, auto_correct:true
  config.vm.network  "forward_port", guest: 4848, host: 4848

# config.vm.forward_port 80, 8888
# config.vm.forward_port 443, 9999
# config.vm.forward_port 4848, 4848

#  config.vm.customize ["modifyvm", :id, "--memory", 1024]


  config.vm.provider "virtualbox" do |v|
        v.customize ["modifyvm", :id, "--memory", "2048"]
  end

  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "manifests"
    puppet.module_path = "modules"
    puppet.manifest_file  = "init.pp"
  end
  
  
end
