Vagrant.configure("2") do |config|

  config.vm.define "box2" do |box2|
    box2.vm.box = "ubuntu/bionic64"
    box2.vm.network :public_network, :mode => "bridge", :bridge => 'br0', :dev => 'eno1'
    box2.vm.provision "shell", inline: "/bin/cat /vagrant/authorized_keys.txt >> /home/vagrant/.ssh/authorized_keys"
  end

  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--memory", 1024]
  end

  config.vm.provision :ansible do |ansible|
     ansible.playbook = 'playbook.yml'
  end

end
