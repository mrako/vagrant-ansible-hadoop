Vagrant.configure("2") do |config|
  config.vm.box      = "ubuntu/trusty64"

  config.vm.network :forwarded_port, guest: 80, host: 8888, auto_correct: true

  config.ssh.forward_agent = true

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", 2048]
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "provisioning/playbook.yml"

    ansible.host_key_checking = false

    ansible.verbose = "v"
  end
end
