Vagrant.configure("2") do |config|
  config.vm.define "chef" do |chef|
    chef.vm.box = "ubuntu/precise64"
    chef.vm.hostname = 'chef'
    chef.vm.box_url = "ubuntu/precise64"

    chef.vm.network :private_network, ip: "192.168.56.101"

    chef.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "chef"]
    end
  end

  config.vm.define "jenkins" do |jenkins|
    jenkins.vm.box = "ubuntu/precise64"
    jenkins.vm.hostname = 'jenkins'
    jenkins.vm.box_url = "ubuntu/precise64"

    jenkins.vm.network :private_network, ip: "192.168.56.102"

    jenkins.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "jenkins"]
    end
  end
end