Vagrant.configure("2") do |config|

  config.vm.define "ansible-role-pip" do |box1|
    box1.vm.box = "peru/ubuntu-18.04-server-amd64"
    box1.vm.box_version = "20200806.01"
    box1.vm.network "public_network", :dev => "br0", :mode => 'bridge', :type => "bridge"
  end

  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--memory", 512]
  end

  config.vm.provision :ansible do |ansible|
     ansible.playbook = 'playbook.yml'
  end

end
